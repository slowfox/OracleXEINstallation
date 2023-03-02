# Oracle Linux 8 / Oracle Database XE

### Fresh Install of Oracle Linux 8

This guide assumes that you have installed Oracle Linux 8, as available from Oracle here: [https://yum.oracle.com/oracle-linux-isos.html](https://yum.oracle.com/oracle-linux-isos.html).

This guide was written using VMWare Workstation 17 Player under Windows 11.


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


### Install the RPM

The .rpm will probably have been saved to the Downloads folder: Right Click and Select _Open with Software Install..._


### Reboot, Update, Reboot

This is paranoia talking, but having installed the RPM, reboot, check for updates and, if any, reboot again.










