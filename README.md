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

#### October
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
10/25/2021: I (zurgeg) haven't been posting much, but:

##### `savedata.download`:
- Response starts with a bunch of padding.
- Then the item ID in hex, and likely the number of that item
- Pokemon are likely stored after the 80 byte (this means that each item must be `0x4` bytes long, because you get 20 items, 80/4 = 20) item response
- You can have up to 10 Pokemon in the response. I'll need to do a bit of research later.

4/8/2022: pog
##### `savedata.download`:
- Byte 0x01 = If not zero, triggers 1320x, where x is the number
- Byte 0x02 = Triggers comm error if not zero
- Byte 0x03 = Triggers comm error if not zero
- Byte 0x04 = Triggers comm error if not zero
- Byte 0x05-0x80 onward = padding
- Byte 0x81-0xD1(?) = Pokemon
  Pokemon Structure:
  Byte 0x00-0x01 = Species
  Byte 0x02-0x03 = ???
  Byte 0x04-0x05 = ???
  Byte 0x06-0x07 = ???
  Byte 0x08 = ???
- Byte 0xD2-0xD5 = padding?
- Byte 0xD6 = Padding?
- Byte 0xD7 = Padding?
- Byte 0xD8 = Padding?
- Byte 0xD9 = Download musicals?
Note: when 0xD6-D8 are set to 0x01, the pokemon will level up by 50?

## Credits
zurgeg: Did some research, found the Internet Archive link

forevertoocat: Took interest in the project and joined the team.

## Files
`main.swf`: Obviously the main thing

`pdw.swf`: Likely assets?
