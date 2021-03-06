---
title: Wox
layout: default
---

## Wox - An effective launcher for windows

[https://github.com/Starli0n/Tool_Wox](https://github.com/Starli0n/Tool_Wox)

{:toc}


### Install

 * [Download Wox](http://www.getwox.com)
 * App is installed here `%AppData%\..\Local\Wox\`

Personal settings are located in `%AppData%\Wox\` directory. [(No more Portable version)](https://github.com/Wox-launcher/Wox/issues/629)

Be aware that at that time (v.1.3.183), Wox does not [expand environment variables](https://github.com/Wox-launcher/Wox/issues/816)

[[Wox Documentation]](http://doc.getwox.com/en/index.html)

---

### Settings

#### General

![Settings-General](Settings-General.bmp)


#### Plugin

![Settings-Plugin](Settings-Plugin.bmp)

* Hello World CSharp <br/>
    ☑ Disable

* Hello World Python <br/>
    ☑ Disable

* Everything <br/>
    ☑ Disable

* Folder
    * `C:\xampp\htdocs`
    * `D:\Dev`
    * `D:\Downloads`
    * `D:\Source`
    * `D:\Tools`<br/>
    `%AppData%\Wox\Settings\Plugins\Wox.Plugin.Folder\Settings.json` [[Tool_Wox]](https://github.com/Starli0n/Tool_Wox/blob/master/Settings/Plugins/Wox.Plugin.Folder/Settings.json)

* Program
    * `%TOOLS%\FirefoxPortable`
    * `%TOOLS%\System`
    * `%TOOLS%\cmder_mini`
    * `%TOOLS%\SublimeText`<br/>
    (Add with `Max Depth = 0`)<br/>
    `%AppData%\Wox\Settings\Plugins\Wox.Plugin.Program\Settings.json` [[Tool_Wox]](https://github.com/Starli0n/Tool_Wox/blob/master/Settings/Plugins/Wox.Plugin.Program/Settings.json)


* Web Searches
    * Rename `lucky` to `l`

Title | Action keywords | URL
------|-----------------|----
`WordReference` | `wr` | `http://www.wordreference.com/enfr/{q}`
`Les Numériques` | `num` | `http://www.lesnumeriques.com/recherche?q={q}`


#### Theme

* Dark


#### Hotkey

Wox Hotkey `Alt + Space`

Hotkey | Action keywords | Action
-------|-----------------|-------
`Ctrl + Shift + V` | `cb·` | Clipboard
`Alt + G` | `g·` | Google search
`Ctrl + Alt + L` | `l·` | Google Lucky
`Ctrl + Alt + T` | `wr·` | Wordreference

Or in `%AppData%\Wox\Settings\Settings.json` [[Tool_Wox]](https://github.com/Starli0n/Tool_Wox/blob/master/Settings/Settings.json)

````
  "CustomPluginHotkeys": [
    {
      "Hotkey": "Ctrl + Shift + V",
      "ActionKeyword": "cb "
    },
    {
      "Hotkey": "Alt + G",
      "ActionKeyword": "g "
    },
    {
      "Hotkey": "Ctrl + Alt + T",
      "ActionKeyword": "wr "
    },
    {
      "Hotkey": "Ctrl + Alt + L",
      "ActionKeyword": "l "
    }
  ]
````


#### Proxy

Server `proxy.com` Port `8080`

---

### Install plugins

[Install plugin](http://doc.getwox.com/en/plugin/install_plugin.html) `wpm install <plug-in name>`

* `wpm install Clipboard History`
* `wpm install Dash.Doc`
* `wpm install Remove USB`
* `wpm install Wox.Plugin.ProcessKiller`
* `wpm install Wox.Plugin.Runner`

[Plugin list](http://www.getwox.com/plugin)

---

[[HOME]](../index.html)
