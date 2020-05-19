# Remote Desktop

This repo contains files and instructions to set up VNC server on Linux.

NOTE: This has been tested on the following:
 - Kubuntu 18.04
 - KDE Neon (18.04 base)
 - Kubuntu 20.04
 - Arch Linux

## Initial install instructions

 0. Since this is a remote _desktop_ setup, it's assumed that your server has one of the linux desktop environments installed.

 1. Install `tigervnc`
    ```sh
    $ sudo apt install tightvncserver
    ```

 2. Run the `vncserver` command to set a VNC password. This will also create the default configuration files.
    ```sh
    $ vncserver
    ```
 
 3. Copy xstartup file. Ensure xstartup is executable
    ```sh
    $ chmod +x xstartup
    ```

 4. Modify or replace the vnserver@.service file

 5. On the client side, set up ~/.ssh/config file from the ssh-config.template

## Other helpful commands

 - To reset the password for the vnc server
    ```sh
    $ vncpasswd
    ```

 - To kill running vncserver
    ```sh
    # 0 can be replaced by display/instance number being used
    $ vncserver -kill :0
    ```

Relevant Links:

 - TigerVNC website - [tigervnc]
 - ArchWiki page for TigerVNC - [ArchWiki][arch-tigervnc]
 - VNC Server man page - [vncserver(1)][vncserver-man]
 - Systemd Unit man page - [systemd.unit(5)][systemd-unit-man]


[tigervnc]: <https://tigervnc.org/>
[arch-tigervnc]: <https://wiki.archlinux.org/index.php/TigerVNC>
[vncserver-man]: <https://linux.die.net/man/1/vncserver>
[systemd-unit-man]: <https://www.freedesktop.org/software/systemd/man/systemd.unit.html>
