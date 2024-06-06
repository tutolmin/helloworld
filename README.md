Instructions taken from https://wiki.debian.org/SimplePackagingTutorial

1. Skeleton structure
```
cd task2/helloworld/
/usr/bin/dh_make -c gpl2 --createorig -y
```
3. Source package 
```
dpkg-source -b .
```
4. Building the binary package
```
dpkg-buildpackage -b -uc -us
```
5. Generated files
```
lh@lh-VPCSA35GG:~/task2$ tree .
.
├── helloworld
│   ├── debian
│   │   ├── changelog
│   │   ├── compat
│   │   ├── control
│   │   ├── copyright
│   │   ├── debhelper-build-stamp
│   │   ├── files
│   │   ├── helloworld
│   │   │   ├── DEBIAN
│   │   │   │   ├── control
│   │   │   │   └── md5sums
│   │   │   └── usr
│   │   │       └── share
│   │   │           └── doc
│   │   │               └── helloworld
│   │   │                   ├── changelog.Debian.gz
│   │   │                   ├── copyright
│   │   │                   └── README.Debian
│   │   ├── helloworld.cron.d.ex
│   │   ├── helloworld.doc-base.EX
│   │   ├── helloworld-docs.docs
│   │   ├── helloworld.substvars
│   │   ├── manpage.1.ex
│   │   ├── manpage.sgml.ex
│   │   ├── manpage.xml.ex
│   │   ├── menu.ex
│   │   ├── postinst.ex
│   │   ├── postrm.ex
│   │   ├── preinst.ex
│   │   ├── prerm.ex
│   │   ├── README.Debian
│   │   ├── README.source
│   │   ├── rules
│   │   ├── source
│   │   │   └── format
│   │   └── watch.ex
│   ├── helloworld
│   ├── helloworld.c
│   └── Makefile
├── helloworld_1.2-1_amd64.buildinfo
├── helloworld_1.2-1_amd64.changes
├── helloworld_1.2-1_amd64.deb
├── helloworld_1.2-1.debian.tar.xz
├── helloworld_1.2-1.dsc
└── helloworld_1.2.orig.tar.xz
```
6. Installation
```
sudo apt install ./helloworld_1.2-1_amd64.deb --fix-broken
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Note, selecting 'helloworld' instead of './helloworld_1.2-1_amd64.deb'
The following additional packages will be installed:
  vim
Suggested packages:
  ctags vim-doc vim-scripts
The following NEW packages will be installed:
  helloworld vim
0 upgraded, 2 newly installed, 0 to remove and 5 not upgraded.
Need to get 1 156 kB/1 158 kB of archives.
After this operation, 2 870 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 /home/lh/task2/helloworld_1.2-1_amd64.deb helloworld amd64 1.2-1 [2 140 B]
Get:2 http://ru.archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim amd64 2:8.0.1453-1ubuntu1.13 [1 156 kB]
Fetched 1 156 kB in 3s (423 kB/s)
Selecting previously unselected package vim.
(Reading database ... 239680 files and directories currently installed.)
Preparing to unpack .../vim_2%3a8.0.1453-1ubuntu1.13_amd64.deb ...
Unpacking vim (2:8.0.1453-1ubuntu1.13) ...
Selecting previously unselected package helloworld.
Preparing to unpack .../helloworld_1.2-1_amd64.deb ...
Unpacking helloworld (1.2-1) ...
Setting up vim (2:8.0.1453-1ubuntu1.13) ...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdiff) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rvim (rvim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vi (vi) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/view (view) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/ex (ex) in auto mode
Setting up helloworld (1.2-1) ...
```   
8. Deinstallation
```
sudo apt remove helloworld
```
9. Running
```
lh@lh-VPCSA35GG:~/task2$ helloworld
Hello, World!lh@lh-VPCSA35GG:~/task2$ 
```
