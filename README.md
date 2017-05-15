# rutorrent-docker

This is a completely funcional Docker image with rutorrent 3.7, rtorrent 0.9.6, libtorrent 0.13.6 and a lot of plugins 
for rutorrent, like autodl-irssi, filemanager, fileshare and other useful ones.

Based on Alpine Linux, which provides a very small size. Includes plugins:
logoff
fileshare
filemanager
pausewebui
mobile
ratiocolor
force_save_session
showip
...

Also installed and selected by default this awesome theme:
club-QuickBox

Also includes MaterialDesign theme as an option.

Tested and working on Synology and QNAP, but should work on any x86_64 devices.

Instructions:
Map any local port to 443 for SSL rutorrent access
Map any local port to 51415 for rtorrent
Map a local volume to /config (Stores configuration data, including rtorrent session directory. Consider this on SSD Disk)
Map a local volume to /downloads (Stores downloaded torrents)

Sample run command:

docker run -d --name=rutorrent \
-v /share/Container/rutorrent-docker/config:/config \
-v /share/Container/rutorrent-docker/downloads:/downloads \
-e PGID=0 -e PUID=0 -e TZ=Europe/Madrid \
-p 9443:443 \
-p 51415-51415:51415-51415 \
romancin/rutorrent:latest

Rememeber editing /config/rtorrent/rtorrent.rc with your own settings, specially your watch subfolder configuration.
