# Centos

This folder contains the Centos utility scripts.  The following
scripts are provided:

- yumroot : must be run as root, wrapper around "yum".
- mkroot : calls yumroot to create a rootfs.

To create the rootfs tarball:

- tar -C <rootdir> -Jcf centos-<release>-roofs.tar.xz
