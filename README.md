# docker compose stack for NZB apps
(sabnzbd, sonarr, radarr, lidarr & bazarr)

*This is intended for use on a Linux machine*

The **.yml** file contains everything you need for a stack to handle nzb files.  
The **.env** file contains variables that you'll want to set and pass into Portainer (or however else you chose to do it).  

**Explanation of the variables:**  
`uid` = the user id you will run the stack as.  
`gid` = the group ID (the way I have it configured is one that has read/write access to the media location).  
`tz` = TimeZone.  
`rootConf` = the root location for your config files for the various apps in the stack.  
`rootDL` = the root location of where sabnzbd will download files to.  
`rootMedia` = the root of where your media location is mounted.  

**Considerations for config and media folders.**  
- Config folder. Rather than use a Docker volume, the compose file uses a folder that resides on your host machine. The location of which will need to be accessible by the `uid`/`gid` that you specify in the variables. Create sub-folders for sabnzbd, sonarr, radarr, lidarr & bazarr. The config will be populated once the containers are started.  
- Download root folder will need to be changed in sabnzbd. Change the folder options to /downloads/incomplete and /downloads/complete (you may need to create those on your host first). If you don't do this, then sab will download files within it's own container, and the other apps will not be able to access them.  
- The media root is where you'll want to then have sub-folders for Movies, TV and Music. Sonarr, Radarr and Lidarr by default will use a different location, so once you've started the stack, you'll need to re-configure these settings to point the mounted /media path in each app. You may also need to add /downloads/complete in the Download Clients > Remote Path Mappings for each app.
