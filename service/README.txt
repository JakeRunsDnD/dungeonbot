Welcome to the service directory!

This is currently under construction. I haven't
even run these scripts yet, but I'm working on
a sweet little perma-live process for tavernbot,
which will make updating it super easy. 

For now, these random scripts will sit here
with no indication whatsoever as to how they
should be used. Documentation and tested
versions of the scripts coming soon!

Cheers.

These are notes, not documentation - though they 
might be useful, I literally just bricked my pi
trying some systemd fanciness, 

SYSV SETUP:
$ cp init-script.sh /etc/init.d/tavernbot
$ service tavernbot status
Should recognize it, haven't tested
$ service tavernbot start
TODO Find the cmd to set this service to run at boot

SYSTEMD SETUP:
Edit tavernbot.service, ensure the node path is right (node8+) and the user is right (not root)
$ systemd --version
If you have 236+, uncomment the StandardOutput/Error lines in the service if you'd like to output
logs and errors to custom locations. Else it's journalctl for you
$ cp tavernbot.service /etc/systemd/system/
$ systemctl daemon-reload
$ systemctl status tavernbot.service # It should say 'not loaded'
$ systemctl enable tavernbot.service
$ systemctl start tavernbot.service
