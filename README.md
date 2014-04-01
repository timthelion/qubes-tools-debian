Installing the debian qubes-tools
=================================

1. Clone this repository into an AppVM.

2. Install debian into an HVM, setting the default user to be named user.

3. Start the debian hvm with the following command in dom0:

    $ qvm-start debian-hvm --cdrom=debian-qubes-tools-build-vm:/path/to/qubes-tools-debian.iso

4. Mount the iso image, cd into it, and run the `qubes-tools-install` script.

Building the debian qubes-tools
===============================

1. Clone this repository into an AppVM

2. Run the `qubes-tools-build` command.

**Note1:** This command will take a long time(45 minutes) the first time it is run.  Following times it takes just a few secconds.

**Note2:** It may fail the first time you run it,  try repeating the command if it fails to create an iso image.

**Note3:** This command will clone several git repositories into a subdirectory named `sources` you must manually update these repositories with `git pull` if you want to rebuild the iso with updated code.

**Note4:** If you edit the source code in the `sources` directories, then you may have to pass the `qubes-tools-build` command the `--git-ignore-new` option in order to get it to build sucessfully.
