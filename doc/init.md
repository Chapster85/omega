Sample init scripts and service configuration for omegad
==========================================================

Sample scripts and configuration files for systemd, Upstart and OpenRC
can be found in the contrib/init folder.

    contrib/init/omegad.service:    systemd service unit configuration
    contrib/init/omegad.openrc:     OpenRC compatible SysV style init script
    contrib/init/omegad.openrcconf: OpenRC conf.d file
    contrib/init/omegad.conf:       Upstart service configuration file
    contrib/init/omegad.init:       CentOS compatible SysV style init script

1. Service User
---------------------------------

All three startup configurations assume the existence of a "omega" user
and group.  They must be created before attempting to use these scripts.

2. Configuration
---------------------------------

At a bare minimum, omegad requires that the rpcpassword setting be set
when running as a daemon.  If the configuration file does not exist or this
setting is not set, omegad will shutdown promptly after startup.

This password does not have to be remembered or typed as it is mostly used
as a fixed token that omegad and client programs read from the configuration
file, however it is recommended that a strong and secure password be used
as this password is security critical to securing the wallet should the
wallet be enabled.

If omegad is run with "-daemon" flag, and no rpcpassword is set, it will
print a randomly generated suitable password to stderr.  You can also
generate one from the shell yourself like this:

bash -c 'tr -dc a-zA-Z0-9 < /dev/urandom | head -c32 && echo'

Once you have a password in hand, set rpcpassword= in /etc/omega/omega.conf

For an example configuration file that describes the configuration settings,
see contrib/debian/examples/omega.conf.

3. Paths
---------------------------------

All three configurations assume several paths that might need to be adjusted.

Binary:              /usr/bin/omegad
Configuration file:  /etc/omega/omega.conf
Data directory:      /var/lib/omegad
PID file:            /var/run/omegad/omegad.pid (OpenRC and Upstart)
                     /var/lib/omegad/omegad.pid (systemd)

The configuration file, PID directory (if applicable) and data directory
should all be owned by the omega user and group.  It is advised for security
reasons to make the configuration file and data directory only readable by the
omega user and group.  Access to omega-cli and other omegad rpc clients
can then be controlled by group membership.

4. Installing Service Configuration
-----------------------------------

4a) systemd

Installing this .service file consists on just copying it to
/usr/lib/systemd/system directory, followed by the command
"systemctl daemon-reload" in order to update running systemd configuration.

To test, run "systemctl start omegad" and to enable for system startup run
"systemctl enable omegad"

4b) OpenRC

Rename omegad.openrc to omegad and drop it in /etc/init.d.  Double
check ownership and permissions and make it executable.  Test it with
"/etc/init.d/omegad start" and configure it to run on startup with
"rc-update add omegad"

4c) Upstart (for Debian/Ubuntu based distributions)

Drop omegad.conf in /etc/init.  Test by running "service omegad start"
it will automatically start on reboot.

NOTE: This script is incompatible with CentOS 5 and Amazon Linux 2014 as they
use old versions of Upstart and do not supply the start-stop-daemon uitility.

4d) CentOS

Copy omegad.init to /etc/init.d/omegad. Test by running "service omegad start".

Using this script, you can adjust the path and flags to the omegad program by
setting the Omega NetworkD and FLAGS environment variables in the file
/etc/sysconfig/omegad. You can also use the DAEMONOPTS environment variable here.

5. Auto-respawn
-----------------------------------

Auto respawning is currently only configured for Upstart and systemd.
Reasonable defaults have been chosen but YMMV.
