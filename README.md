Collection of things that don't work.

![](http://nutcom.storage.googleapis.com/images/y-u-no_2403075.jpg)

# launchctl doesn't work in tmux

Cannot load or unload agent/daemon. Reports error like:

(agent is launchctl jargon for a user service, and daemon means system service. wtf?)

```
$ launchctl load ~/Library/LaunchAgents/homebrew.mxcl.influxdb.plist
Could not open job overrides database at: /private/var/db/launchd.db/com.apple.launchd/overrides.plist: 13: Permission denied
launch_msg(): Socket is not connected
```

+ see: http://www.economyofeffort.com/2013/07/29/reattach-to-user-namespace-the-fix-for-your-tmux-in-os-x-woes/
+ solution: don't run launchctl in tmux.
+ reason: https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard#access-to-the-mac-os-x-pasteboard-service

Some namespace thing. See: https://developer.apple.com/library/mac/technotes/tn2083/_index.html#//apple_ref/doc/uid/DTS10003794-CH1-SUBSECTION51
