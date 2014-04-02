Debian Qubes tools
==========================

These scripts can be used to build and install the debian tools for running a debian HVM as guest on qubes.

These packages were prepaired by [Davíð Steinn Geirsson](http://www.dsg.is/qubes/), but the tools themselves were mostly written by the Qubes team.  Thanks to both!

Building the debian qubes-tools
===============================

1. Clone this repository into an AppVM

2. Run the `qubes-tools-build` command.

**Note1:** This command will take a long time(45 minutes) the first time it is run.  Following times it is much faster(though still frustratingly slow).

**Note2:** It may fail the first time you run it,  try repeating the command if it fails to create an iso image.

**Note3:** This command will clone several git repositories into a subdirectory named `sources` you must manually update these repositories with `git pull` if you want to rebuild the iso with updated code.

**Note4:** If you edit the source code in the `sources` directories, then you may have to pass the `qubes-tools-build` command the `--git-ignore-new` option in order to get it to build sucessfully.

Installing the debian qubes-tools
=================================

1. Build these tools in an AppVM.

2. Install debian into an HVM, setting the default user to be named user. Be careful to make sure that it is the 64bit installation!

3. Start the debian hvm with the following command in dom0:

    ````
    $ qvm-start debian-hvm --cdrom=debian-qubes-tools-build-vm:/path/to/qubes-tools-debian.iso
    ````

4. Mount the iso image, cd into it, and run the `qubes-tools-install` script.

    ````
    # mount /dev/cdrom /mnt
    # cd /mnt
    # ./qubes-tools-install
    ```` 

Copyright
=========

The souce code found in this repository is released under the GPLv2 license.  The sourcecode for the binaries found in the .iso image can be downloaded by running the `qubes-tools-build` script, and is also GPLv2.
