# proot4ci

User level chroot/fakeroot for travis-ci

![Build Status](https://api.travis-ci.org/TortugaLabs/proot4ci.png?branch=master)](https://travis-ci.org/TortugaLabs/proot4ci)

File layout:

- mkroots: scripts to create rootfs files...
  - mkroot : main driver script for creating rootfs tar balls
  - alpine.mkroot : Alpine Linux specifics
  - archlinux.mkroot : Arch Linux specifics
  - centos.mkroot : centos specifics
  - yumroot : helper tool for centos.mkroot
- setup: create a rootfs
  - alpine.cfg : Alpine Linux config settings
  - centos.cfg : Centos config settings
  - archlinux.cfg : Arch Linux specific settings

Usage:

- Add this as a submodule
- Add the follwing to your `.travis.yml`

```

language: c
compiler: gcc
install:
- ./proot4ci/setup <flavor> <rootfs>
before_script:
- export PATH=$PATH:$PWD/proot4ci/bin
addons:
 apt:
  packages:
   - libtalloc-dev

```

## NOTES

- Install libtalloc-dev on CentOS.
- Run:
  - setup _flavor_ _rootfs_
- From then on you can do:
  - bin/proot -R _rootfs_ _[commands]_




