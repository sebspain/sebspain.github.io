---
author: sspain
comments: true
layout: post
slug: wd-my-cloud-on-linux
title: Western Digital My Cloud Linux Access
categories:
- linux 
---

I recently bought a [Western Digital My Cloud](http://www.wdc.com/en/products/products2.aspx?id=1140) NAS box for backing up the various computers we have at home.

As has been noted in various parts of the web, despite this being a Linux based box WD have not only failed to provide a Linux client (not that surprising) but they haven't even given basic instructions for mounting shares manually.

Luckily, it's a pretty standard Debian install with a web front end that updates the conf files for samba and nfs when you add a share (or change permissions etc) so it's mounting on Linux is easy.

SMB shares are located at:

```sh
//<IP Address of Server>/<name of share>
```
e.g. for a share called "Photos" my box (IP: 192.168.0.15)

```sh
//192.168.0.15/Photos
```

To mount this on Linux I do the following as root. Obviously there are various other options for the mounting and gid and uid will depend on who you want to own the mount. 

```sh
mkdir -p /NAS/Photos
echo "//192.168.0.10/Photos /NAS/Photos cifs credentials=/root/.nas_cred,gid=1000,uid=1000,rw 0 0" >> /etc/fstab
echo "username=seb
password=<password>" > /root/.nas_cred
chmod 600 /root/.nas_cred
mount /NAS/Photos
```
This will automatically mount on boot.

