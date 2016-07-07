---
title: Cmder
layout: default
---

## Cmder - Portable console emulator for Windows

{:toc}


### Install

* [Download Cmder (mini)](http://cmder.net) (v1.2.9)
* Copy exe to `%TOOLS%\cmder_mini\`
* Add environment variables `%CMDER_ROOT% = %TOOLS%\cmder_mini`


### Init

* Edit `%CMDER_ROOT%\vendor\init.bat`

Assuming `%TOOLS%\PortableGit`, replace

````
:: Check if msysgit is installed
@if exist "%ProgramFiles%\Git" (
    set "GIT_INSTALL_ROOT=%ProgramFiles%\Git"
) else if exist "%ProgramFiles(x86)%\Git" (
    set "GIT_INSTALL_ROOT=%ProgramFiles(x86)%\Git"
) else if exist "%CMDER_ROOT%\vendor" (
    set "GIT_INSTALL_ROOT=%CMDER_ROOT%\vendor\git-for-windows"
)
````

by

````
:: Check if msysgit is installed
@if exist "%TOOLS%\PortableGit" (
    set "GIT_INSTALL_ROOT=%TOOLS%\PortableGit"
) else if exist "%ProgramFiles%\Git" (
    set "GIT_INSTALL_ROOT=%ProgramFiles%\Git"
) else if exist "%ProgramFiles(x86)%\Git" (
    set "GIT_INSTALL_ROOT=%ProgramFiles(x86)%\Git"
) else if exist "%CMDER_ROOT%\vendor\git-for-windows" (
    set "GIT_INSTALL_ROOT=%CMDER_ROOT%\vendor\git-for-windows"
)
````


* Remove `%GIT_INSTALL_ROOT%\usr\bin;` because `which` does not do its job (use `which=gs which $*` in `aliases` instead)

````
:: Add git to the path
@if defined GIT_INSTALL_ROOT (
    ::%GIT_INSTALL_ROOT%\usr\bin;
    set "PATH=%GIT_INSTALL_ROOT%\bin;%GIT_INSTALL_ROOT%\share\vim\vim74;%PATH%"
    :: define SVN_SSH so we can use git svn with ssh svn repositories
    if not defined SVN_SSH set "SVN_SSH=%GIT_INSTALL_ROOT:\=\\%\\bin\\ssh.exe"
)
````


### Aliases

* Edit `%CMDER_ROOT%\config\aliases` to add some aliases

````
e.=explorer .
gl=git log --oneline --all --graph --decorate  $*
gv=g --version
clear=cls
hist=type %CMDER_ROOT%\config\.history
clearh=echo.>%CMDER_ROOT%\config\.history
chelp=type %CMDER_ROOT%\config\aliases
unalias=alias /d $1
upath=spath -u
pwd=cd
cd=cd /d $*
..=cd..
ll=gs ls -l --show-control-chars -F --color $*
which=gs which $*
ph=pushd $*
pp=popd $*
subld=subl -n %CD%

slist=tasklist /FI "IMAGENAME eq w3wp.exe"
skill=taskkill /F /FI "IMAGENAME eq w3wp.exe"
tfs_clean=tfpt uu /noget /r *
````

* Fixing the [issue](https://github.com/cmderdev/cmder/issues/684) with expanding environment variables in aliases
    * Backup `%CMDER_ROOT%\vendor\clink`
    * Replace by [this one](https://www.dropbox.com/sh/hqbrpkf0dpmmizq/AADIJ4G5gjJ59JfFmr-3-Qc0a/20150923_1abb57/clink_DEV.zip?dl=0)

### Settings

* `Main > Size & Pos`
☑ Auto save window size and position on exit

* `Keys & Macro`
Global Ctrl+² Minimize/Restore (Quake-style hotkey also)

---

[[HOME]](../index.html)
