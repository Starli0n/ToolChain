---
title: VisualStudio
layout: default
---

## Visual Studio

[https://www.visualstudio.com](https://www.visualstudio.com)

{:toc}


### Settings

`Tools > Options...`

* `Environment`
	* `Keyboard` <br/>
	![Settings-Keyboard](Settings-Keyboard.bmp)

* `Projects and Solutions` > <br/>
	☑ `Track Active Item in Solution Explorer`

* `Source Control`
	* `Visual Studio Team Foundation Server` > `[Configure User Tools...]`
	![Settings-ConfigureTool](Settings-ConfigureTool.bmp)<br/>
	Command: `C:\Program Files (x86)\WinMerge\WinMergeU.exe`<br/>
	Arguments: `/ub /dl %6 /dr %7 %1 %2`

* `Text Editor`
	* `All Languages` <br/>
	☑ `Line numbers`
		* `Scroll Bars`<br/>
		![Settings-Behavior](Settings-Behavior.bmp)

Using double click to compare instead of opening <br/>
`HKCU\Software\Microsoft\VisualStudio\14\TeamFoundation\SourceControl\Behavior\DoubleClickOnChange (DWORD) 1`


### Customize

* `Tools > Customize...`
![Settings-Customize](Settings-Customize.bmp)

* `[Add Command...]`
![Settings-AddCommand](Settings-AddCommand.bmp)

`External Command 7`: Cmder<br/>
`External Command 8`: Sublimet Text


#### Cmder

![ExternalTools-Cmder](ExternalTools-Cmder.bmp)

* Title: `λ Cmder`
* Command: `%CMDER_ROOT%\vendor\conemu-maximus5\ConEmu.exe`
* Arguments: `"/here" /icon %CMDER_ROOT%\icons\cmder.ico /single /cmd cmd /k "%CMDER_ROOT%\vendor\init.bat"`
* Initial directory: `$(ItemDir)`


#### Sublime Text

![ExternalTools-SublimeText](ExternalTools-SublimeText.bmp)

* Title: `Sublime Text`
* Command: `%TOOLS%\SublimeText\sublime_text.exe`
* Argument: `$(ItemPath)`


### Clean Recent Items

Erase the registry key `[HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\MRUItems]` using [`%TOOLS%\System\VSCleanRecent.reg`](https://github.com/Starli0n/Tool_System/blob/master/VSCleanRecent.reg) or the alias [`vsclean`](https://github.com/Starli0n/Tool_Cmder/blob/master/config/aliases)


### Extensions

[TODO]


---

[[HOME]](../index.html)
