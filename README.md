# docker compose stack for NZB apps
(sabnzbd, sonarr, radarr, lidarr & bazarr)

*This is intended for use on a Linux machine*

The **.yml** file contains everything you need for a stack to handle nzb files.  
The **.env** file contains variables that you'll want to set and pass into Portainer (or however else you chose to do it).  

**Explanation of the variables:**  
`uid` = your user ID.  
`gid` = your group ID (one that can manage the media location).  
`tz` = TimeZone.  
`rootConf` = the root location for your config files for the various apps in the stack.
`rootDL` = the root location of where sabnzbd will download files to. sabnzbd will be configured by default to a different location, so make sure on your host machine you have an incomplete and complete folder, then in sabnzbd change the temporary download location to /downloads/incomplete and completed to /downloads/complete.  
`rootMedia` = the root of where your media location is mounted. You're best off creating a Movies, TV and Music folder off of the root. Then in Sonarr, Radarr and Lidarr point the folders to /media/(relevant sub-folder)  

**Considerations for config and media folders.**  
- Config folder. Rather than use a Docker volume, the compose file uses a folder that resides on your host machine. The location of which will need to be accessible by the `uid`/`gid` that you specify in the variables. Create a sabnzbd, sonarr, radarr & lidarr folder. The config will be populated once the containers are started.  
- Download root folder will need to be changed in sabnzbd, so change the folder options to /downloads/incomplete and /downloads/complete (you may need to create those on your host first.  
- The media root is where you'll want to then have sub-folders for Movies, TV and Music. Sonarr, Radarr and Lidarr by default will use a different location, so once you've started the stack, you'll need to re-configure these settings to point the mounted /media path in each app.  
