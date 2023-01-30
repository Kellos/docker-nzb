# docker compose stack for NZB related apps

The .yml file contains everything you need for a stack to handle nzb files.
The .env file contains variables that you'll want to set and pass in in Portainer (or however else you chose to do it).

uid = your user ID
gid = your group ID (one that can manage the media location)
tz = TimeZone
rootConf = the root location for your config files for the various apps in the stack
rootDL = the root location of where sabnzbd will download files to
rootMedia = the root of where your media location is mounted.
