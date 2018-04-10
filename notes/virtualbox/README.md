### VirtualBox notes

###### VirtualBox Guest Additions on CentOS/RHEL 7.x

[source article](https://www.if-not-true-then-false.com/2010/install-virtualbox-guest-additions-on-fedora-centos-red-hat-rhel/)

VirtualBox Guest Additions is special software that can be installed inside Linux virtual machines to improve performance and make integration much more seamless.
Among the features provided by these VirtualBox Guest Additions are mouse pointer integration and arbitrary screen solutions (e.g. by resizing the guest window).

Steps:
- add EPEL repo using:
  `rpm -Uvh http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-9.noarch.rpm`
- install the gcc and kernel sources:
  `yum install gcc kernel-devel kernel-headers dkms make bzip2 perl`
- set KERN_DIR env var, example:
  `KERN_DIR=/usr/src/kernels/3.10.0-229.el7.x86_64`
- mount Guest Additions using `Devices > Install Guest Additions` menu
- install Guest Additions using
  ```
  cd /media/VirtualBoxGuestAdditions
  ./VBoxLinuxAdditions.run
  ```
