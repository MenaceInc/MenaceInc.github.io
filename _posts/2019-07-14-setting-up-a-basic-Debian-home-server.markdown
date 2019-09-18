---
layout: post
title: "Setting up a basic Debian home server \[ssh, samba, nextcloud, pi-hole, openvpn\]"
date: "2019-07-14 09:00:00 +0000"
---

Setting up a simple home server using some old hardware is pretty easy with using something like Debian Linux. When done, you should have a nice and simple server which all of your family can use.

### Basic install

su

login as root

apt update
apt upgrade
apt install sudo
adduser john sudo

logout
logout

login as user


Recommend zsh

sudo apt install git curl zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"


### Setup SSH and some server hardening



### Install and setup Samba

sudo apt install samba

ensure have drives mounted and directories created that want to have available

sudo cp /etc/samba/smb.conf /etc/samba/backup.conf

sudo nano /etc/samba/smb.conf




### Install and setup Pi-hole



### Install and setup Nextcloud



### Install and setup OpenVPN



### Setup email alerts for hardware/software issues