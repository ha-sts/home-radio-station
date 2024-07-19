HA-STS Home Radio Station
=========================

A LiquidSoap based web radio station for the homeland.

Setup Notes
-----------

These are notes for now.  Eventually they'll be converted into a proper install guide.

### Install Ubuntu

1. Install the latest ubuntu.  Make sure to use the server version and install openssh.

1. SSH into the server.

1. Update all the packages on the system.  At this point, if desired, any extra packages can be uninstalled.

1. Install IceCast2 and LiquidSoap: `apt install icecast2 liquidsoap`

1. Configure the mount for music.  In this case, using SMB.  https://wiki.ubuntu.com/MountWindowsSharesPermanently

      * `apt install cifs-utils`
	  * `mkdir /tank`
	  * `mkdir /tank/music`
	  * Edit `/etc/fstab`
	  * Something like `//<server>/music    /mnt/music     cifs    username=readonly,password=password,iocharset=utf8      0       0`
	  * `mount -a`

1. Configure IceCast2 for stations.  FIXME: Is this really needed?  Looks like no.  Stations won't show up unless a source exists.
   * Old Country
   * Punk Rock
   * 70s Rock
   * 80s Rock
   * 90s Rock & Alternative
   * Nerd Core

1. Create playlists (NOTE TO SELF: Commit the generator to repo with example).

1. Create the station generation script (NOTE TO SELF: Commit this to repo).

### Still To Do: Server

1. Configure LiquidSoap (started, but need more)

1. Setup mDNS

1. Some sort of server or process for liquidsoap to get the "next song" for each station
   Is the playlist fine, or is a UI needed?  Wouldn't mind having this come from a python server so it can be
   part of a music manager service (similar to plex, but without the new streaming crap in their app).

### Still To Do: Client

1. Figure station selection buttons

1. Make a case

1. Figure out how to control a player to connect to different stations and output via DAC
