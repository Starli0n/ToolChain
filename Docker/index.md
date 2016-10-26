---
title: Docker
layout: default
---

## Docker Toolbox

[https://www.docker.com](https://www.docker.com)

{:toc}

### boot2Docker

#### First Time

* Delete `~/.docker` (Except `~/.docker/machine/cache/boot2docker.iso`)
* Close VirtualBox, Delete `.VirtualBox`, Open and Close it again
* Create a VM `> docker-machine create --driver virtualbox default`
* See how to configure the shell `> docker-machine env default`
* Login to the VM `> docker-machine ssh default`
* Credentials
	* default password: `tcuser`
	* Use ssh keys
	```sh
	> cp $HOME/.docker/machine/machines/default/id_rsa.pub $HOME/.ssh/id_docker_rsa.pub
	> cp $HOME/.docker/machine/machines/default/id_rsa $HOME/.ssh/id_docker.pub
	```

Folders keep intact after a reboot of the VM
* `/var/lib/docker`
* `/var/lib/boot2docker`


### How To Add Bash to the VM

boot2docker is based on Tiny Core Linux. Login to the VM:

* Load bash with tce without install `> tce-load -w bash.tcz`
* Files are downloaded in `/tmp/tce/optional`
* Archive the files
```sh
> cd /tmp/tce/optional
> tar -cf /var/lib/boot2docker/tce.tar *

```

Install bash after the boot of the VM,  in `/var/lib/boot2docker/bootlocal.sh` add

```sh
> tar -xf /var/lib/boot2docker/tce.tar -C /tmp/tce/optional/
> su - docker -c "tce-load -i bash.tcz"

> ln -s /var/lib/boot2docker/rsub /usr/local/bin/rsub
```

Check the installation `> la /usr/local/tce.installed`

Backup `tce.tar` if the VM is recreated `> scp docker@ip:/var/lib/boot2docker/tce.tar .`


### Edit VM files remotely using Sublime Text

Download `rmate`

```
> cd /var/lib/boot2docker
> sudo wget -O rsub https://raw.github.com/aurora/rmate/master/rmate
> sudo chmod a+x rsub
```

Install `rsub` after the boot of the VM,  in `/var/lib/boot2docker/bootlocal.sh` add
```sh
> ln -s /var/lib/boot2docker/rsub /usr/local/bin/rsub
```

Backup `rsub` if the VM is recreated `> scp docker@ip:/var/lib/boot2docker/rsub .`


### Aliases

* [Windows](https://github.com/Starli0n/Tool_Cmder/blob/master/config/aliases)
* [macOS](https://github.com/Starli0n/SublimeUser/blob/master/Resources/OSX/HOME/.MacOSX/.bashrc)
