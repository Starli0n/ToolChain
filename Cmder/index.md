---
title: Cmder
layout: default
---

## Cmder - Portable console emulator for Windows

[https://github.com/Starli0n/Tool_Cmder](https://github.com/Starli0n/Tool_Cmder)

{:toc}


### Install

* [Download Cmder (mini)](http://cmder.net) (v1.3.4)
* Copy exe to `%TOOLS%\cmder_mini\`
* Add environment variables `%CMDER_ROOT% = %TOOLS%\cmder_mini`
* Change to a [powerline prompt](https://github.com/AmrEldib/cmder-powerline-prompt)
	* Download [powerline-fonts](https://github.com/powerline/fonts) to `%CMDER_ROOT%\vendor\powerline-fonts`
	* Open `%CMDER_ROOT%\vendor\powerline-fonts\Hack\Hack-Regular.ttf`
	* Click on `Install` to install it on the system
	* Download the last version of `powerline_prompt.lua` file, and place it in `%CMDER_ROOT%\config` folder
		* Replace `prompt = "\x1b[37;44m{cwd} {git}{hg}\n\x1b[1;30;40m{lamb} \x1b[0m"`
		* By `prompt = "\x1b[37;44m{cwd} {git}{hg}\n\x1b[1;39;40m{lamb} \x1b[0m"`
	* Restart Cmder
	* Change the alternative font to `Hack` in the `Main`settings
	* Add to `Unicode ranges`: `E0A0; E0B0;`
	* Register Cmder in admin mode with `cmder.exe /REGISTER ALL` for a shell integration
	* Update shell integration with the script [CmderHere.reg](https://github.com/Starli0n/SublimeUser3/blob/master/CmderHere.reg)

Advanced Configuration stored in Sublime Text
```bat
mklink %CMDER_ROOT%\config\user-aliases.cmd %SUBL_ROOT%\Data\Packages\User\Resources\Windows\HOME\user-aliases.cmd
mklink %CMDER_ROOT%\config\powerline_prompt.lua %SUBL_ROOT%\Data\Packages\User\Resources\Windows\HOME\powerline_prompt.lua
```


### Aliases

* Edit `%CMDER_ROOT%\config\user-aliases.cmd` to add some [aliases](https://github.com/Starli0n/Tool_Cmder/blob/master/config/user-aliases.cmd)


### Settings

* `Main > Size & Pos`

☑ Auto save window size and position on exit

☑ Snap to desktop edges

![Settings-Main](Settings-Main.bmp)

* `Main > Appearance`

☑ Single instance mode

* `Keys & Macro`

| Type    | Hotkey        | Description                                      |
|---------|---------------|--------------------------------------------------|
| Global  | Ctrl+²        | Minimize/Restore (Quake-style hotkey also)       |
| User    | Ctrl+Shift+T  | Create new console (after ‘Create confirmation’) |
| User    | Ctrl+F        | Find text in active console                      |
| User    | <None>        | Move active tab leftward                         |
| User    | <None>        | Move active tab rightward                        |
| Macro12 | Win+Alt+Left  | Tab(4, -1); Tab(1);                              |
| Macro13 | Win+Alt+Right | Tab(4, 1); Tab(1);                               |
| Macro14 | Ctrl+,        | Settings dialog: Settings()                      |
| Task    | Ctrl+T        | {cmd::Cmder}                                     |


![Settings-KeysMacro](Settings-KeysMacro.bmp)


### Integrate Cmder to Sublime Text

This is performed with the package [Terminal](https://packagecontrol.io/packages/Terminal) configured in Sublime Text with the batch [Terminal.cmd](https://github.com/Starli0n/SublimeUser3/blob/master/Terminal.cmd)


### PortableApps - Cmder

A skeleton for [PortableApps](https://portableapps.com) is found [there](https://github.com/Starli0n/PortableApps-Cmder)


### Integrate Cmder and Sublime Text seamlessly

[a-neat-way-integrate-cmder-and-sublime-text-seamlessly](http://laravel.io/forum/02-24-2014-a-neat-way-integrate-cmder-and-sublime-text-seamlessly)

* Download a portable version of Sublime Text 3 from [their website](https://www.sublimetext.com/3)
* Extract to `%CMDER_ROOT%\vendor\SublimeText`
* Use `sub` to use Sublime Text integrated to Cmder or `subl` to use the general one.

#### Sublime Text 3 - Settings

* `View > Hide Menu`
* `View > Hide Tabs`
* Open `Preferences > Settings - User`

````
// Settings in here override those in "Default/Preferences.sublime-settings",
// and are overridden in turn by file type specific settings.
{
    "close_windows_when_empty": true,
    "hot_exit": false,
    "remember_open_files": false
}
````


### Upgrade

* Backup folder to `%TOOLS%\cmder_mini_bak\`
* Extract the new exe to `%TOOLS%\cmder_mini\`
* `> copy %TOOLS%\cmder_mini_bak\config\user-aliases.cmd %TOOLS%\cmder_mini\config\user-aliases.cmd`
* `> copy %TOOLS%\cmder_mini_bak\config\powerline_prompt.lua %TOOLS%\cmder_mini\config\powerline_prompt.lua`
* `> echo d | xcopy %TOOLS%\cmder_mini_bak\vendor\SublimeText %TOOLS%\cmder_mini\vendor\SublimeText /e`
* Apply the settings

---

[[HOME]](../index.html)
