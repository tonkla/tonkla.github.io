---
layout: post
title: MetaTrader 5 crashed on the macOS Ventura Apple M1
---

They said,

> The trading platform for Mac OS supports the Apple M1 chip and works reliably on any system version, including Ventura. The installation package is compiled using CrossOver technology...

Since the April 2023 update of [MetaTrader 5](https://www.metatrader5.com/en/terminal/help/start_advanced/install_Mac), I've been unable to open MetaEditor. After uninstalling it from `/Applications` and reinstalling, the new MetaTrader displayed old configurations. To locate where the configurations were stored, I used the following command:

```bash
find / -type d -name "drive_c" -print 2>&1 | fgrep -v "find: "
```

The resulting folders were:

```txt
/System/Volumes/Data/Users/me/Library/Application Support/MetaTrader5/Bottles/metatrader5/drive_c

/System/Volumes/Data/Applications/MetaTrader 5.app/Contents/SharedSupport/metatrader5/support/metatrader5/drive_c

/Users/me/Library/Application Support/MetaTrader 5/Bottles/metatrader5/drive_c

/Applications/MetaTrader 5.app/Contents/SharedSupport/metatrader5/support/metatrader5/drive_c
```

I removed all `MetaTrader 5` folders and reinstalled the application. The first opening was successful, but the MetaEditor still could not be opened. However, a minute later, after an automatic update, even MetaTrader itself couldn't be opened anymore.

Now, I am waiting for the release of a new version of MetaTrader that will fix these bugs.
