# pkmn-dreamland
Place where we research Pokèmon Dream World (Game Sync in particular)

## Terms
For the sake of being concise, I have made a few acronyms:
- DWGS: Dream World Game Sync
- PDW: Pokemon Dream World
- GS: Game Sync
- DW: Dream World

## Why is this project called Dream Land?
It's named Dream Land after Mr. Sandman's Taunt (Saying "Dreeam Laand, Boo!"), and his signature move ("Dreamland Express"). I chose this name because of it's similarity to the real game's name; Dream World.

## Research History
### 2021
#### September
9/8/2021: Research begins on Dream World Game Sync, in hopes of being able to back up the save file to the cloud

9/9/2021: I (zurgeg, the author of this repo) located an [archive on Archive.org](https://archive.org/download/pdw_20191128/pdw-snapshot-2014.7z) containing a snapshot of PDW

9/10/2021: Looks like it's using the URL `en-ds.pokemon-gl.com` for sync communications, this is a huge breakthrough

10/2/2021: The following URLs were located in Pokemon White's executable:
```
en-ds.pokemon-gl.com/dsio/gw?p=account.createdata&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=savedata.upload&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=sleepily.bitlist&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=savedata.download&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=account.playstatus&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=worldbattle.upload&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=worldbattle.download&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=account.create.upload&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
en-ds.pokemon-gl.com/dsio/gw?p=savedata.download.finish&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=account.createdata&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=savedata.upload&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=sleepily.bitlist&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=savedata.download&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=account.playstatus&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=worldbattle.upload&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=worldbattle.download&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=account.create.upload&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
https://en-ds.pokemon-gl.com/dsio/gw?p=savedata.download.finish&gsid=%u&rom=%u&langcode=%u&dreamw=%u&tok=%s
```
TODO: Figure out what these are


## Credits
zurgeg: Did some research, found the Internet Archive link

forevertoocat: Took interest in the project and joined the team.

## Files
`main.swf`: Obviously the main thing

`pdw.swf`: Likely assets?
