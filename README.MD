ALCPlugFix
----------

This is an improved version of ALCPlugFix from [goodwin](https://github.com/goodwin/ALCPlugFix).

The original and this fork tries to fix headphone audio power state issue in non Apple sound card in macOS.

The improvement include:

 - Refactor
 - Add listener when sleep/wake
 - Fix on sleep wake
 - Let you choose `hda-verb` so it don't need be in `$PATH`
 - Enable launching as LauchDaemon
 - Bug fix
 - Install.sh script with update support
 - Uninstall.sh to uninstall ALCPlugFix
 - macOS Catalina support

Install
-------
By default it's code command is for Lenovo ThinkPad(s) with Realtek ALC3232 Audio Codec with Combo Jack, you may need to change that in `fixAudio` function.

Running `sh ./install.sh` will install to `/user/local/bin`.

By default it search `hda-verb` in current work directory, if not found it will search in `$PATH` _(May not work when it is running from LaunchDaemon because it is using as root)_.

Compatible Laptops
------------------
- Lenovo ThinkPad T440P
- Lenovo ThinkPad T440
- Lenovo ThinkPad T440S
- Lenovo ThinkPad L440
- Lenovo ThinkPad X240

Build
-----
`xcodebuild -target ALCPlugFix`

Debug
-----

Add following to launchDaemon file to log to `/tmp/ALCPlugFix.log`, _(or use `log stream`)_

```
	<key>StandardOutPath</key>
	<string>/tmp/ALCPlugFix.log</string>
	<key>StandardErrorPath</key>
	<string>/tmp/ALCPlugFix.log</string>
```

Credits
-----

- Goodwin for creating the Software
- Menchen for the refactoring and new features
- Joshuaseltzer for creating new install.sh and uninstall.sh
- Sniki for maintaining the software
