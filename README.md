# weechat-pushjet

A [WeeChat](https://weechat.org/) plugin that sends highlights and/or private message notifications through [Pushjet](https://pushjet.io/).

### Installation

In WeeChat install the script by typing the following:
```
/script install pushjet.py
```

If you're using the public push server, all you have to do is set the _`secret`_ option in the configuration.

### Options

The plugin allows you to set a few options through the normal WeeChat settings system.  
You'll find all of them under _`plugins.var.python.pushjet`_, and all of them have helpful descriptions.

To set them use _`/set plugins.var.python.pushjet.foo bar`_ or through the [iset.pl](https://weechat.org/scripts/source/iset.pl.html) plugin.

- `host`
	- host for the pushjet api (default: "https://api.pushjet.io")
- `secret`
	- secret for the pushjet api (default: "")
- `level`
	- severity level for the message, from 1 to 5 (low to high) (default: 4)
- `timeout`
	- timeout for the message sending in seconds (>= 1) (default: 30)
- `separator`
	- separator between nick and message in notifications (default: ": ")
- `notify_on_highlight`
	- push notifications for highlights in buffers (on/off) (default: "on")
- `notify_on_privmsg`
	- push notifications for private messages (on/off) (default: "on")
- `notify_when`
	- when to push notifications (away/detached/always/never) (default: "always")
- `ignore_buffers`
	- comma-separated list of buffers to ignore (default: "")
- `ignore_nicks`
	- comma-separated list of users to not push notifications from (default: "")

### Issues

- The currently available version of Pushjet is sending the wrong error codes for errors.  
	This means that if your settings are invalid it's very hard to find out exactly what is wrong.
- Away status can't be checked when receiving private messages
