# docker compose stack for NZB apps
## (sabnzbd, sonarr, radarr, lidarr & bazarr)

The **.yml** file contains everything you need for a stack to handle nzb files.<br />
The **.env** file contains variables that you'll want to set and pass into Portainer (or however else you chose to do it).<br />

**uid** = your user ID.<br />
**gid** = your group ID (one that can manage the media location).<br />
**tz** = TimeZone.<br />
**rootConf** = the root location for your config files for the various apps in the stack.<br />
**rootDL** = the root location of where sabnzbd will download files to.<br />
**rootMedia** = the root of where your media location is mounted.
