# docker compose stack for NZB apps
(sabnzbd, sonarr, radarr, lidarr & bazarr)

*This is intended for use on a Linux machine*

The **.yml** file contains everything you need for a stack to handle nzb files.  
The **.env** file contains variables that you'll want to set and pass into Portainer (or however else you chose to do it).  

Explanation of the variables:  
`uid` = your user ID.  
`gid` = your group ID (one that can manage the media location).  
`tz` = TimeZone.  
`rootConf` = the root location for your config files for the various apps in the stack.  
`rootDL` = the root location of where sabnzbd will download files to.  
`rootMedia` = the root of where your media location is mounted.
