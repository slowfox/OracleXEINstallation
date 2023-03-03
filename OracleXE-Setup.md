# Oracle Linux 8 / Oracle Database XE

### Fresh Install of Oracle Linux 8

This guide assumes that you have installed Oracle Linux 8, as available from Oracle here: [https://yum.oracle.com/oracle-linux-isos.html](https://yum.oracle.com/oracle-linux-isos.html).

This guide was written using VMWare Workstation 17 Player under Windows 11, under the usual _It Works For Me_ guarantee.


### Initial boot

On first boot - having accepted the Oracle License Agreement - log in as a User with administrative rights (that is, they can run `sudo`). _Do not_ log in as `root`.

The update chain below assumes that `httpd` is installed; since it wasn't on my system, I installed it via yum:
   `$ sudo yum install httpd`

Ensure that the VM is connected to the Network, and issue the following:

    $ sudo dnf update
    $ sudo dnf update httpd
    $ sudo yum check-update
    $ sudo yum update
    $ sudo yum update httpd



### Download Oracle XE

Logged into Linux, navigate to Oracle's downloads page for XE: [https://www.oracle.com/database/technologies/xe-downloads.html](https://www.oracle.com/database/technologies/xe-downloads.html), and select the appropriate release for Oracle Linux 8 (OL8).

This will download a .rpm file; it would be sensible to verify the checksum:

    $ sha256sum {filename}

_Hint: Use tab for filename completion_


### Forewarned is Forearmed

During the installation process, we'll be asked to set a couple of passwords; good practice would be to use strong, distinct passwords, but do bear in mind that Oracle has issues with certain characters in passwords, such as the `@` symbol.

You will need to create passwords for `SYS` and `SYSTEM` accounts, so be prepared for this step during installation.


### Install the RPM

We're going to install XE from the command line, rather than using Software Center.

I'm actually `su`-ing to root, here (root password prompt not shown).

    $ cd ~/Downloads
    $ su -
    # rpm -ivh {rpm-filename}

When prompted, run the following command (note: still `su`-ing as `root`):

    # /etc/init.d/oracle-xe-21c configure

Once the installation script has completed, remember to `exit` from the `su` root account!


### Reboot the Machine

Assuming that you set the database to start automatically on reboot, XE should now be up and running.

