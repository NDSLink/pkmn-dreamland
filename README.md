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

## Credits
- @zurgeg: Research and code (Python)
- @kuroppoi: Research and code (Java)

## Styling
1. Refer to yourself in the third person. Using "I" gets confusing in a repo that's supposed to be maintained by multiple people
2. When making comments, make sure they are marked with "Note: (your username)". I.e., Note (@zurgeg).
3. When referring to implemenentations (see the mention of `0x7D` below), find the implementation in both `dream-server` and Entralinked if you can
4. Lastly, when referring to internal documentation within code (i.e., comments), feel free to use either repo, since both **should** have the same documentation

## Structures
### `savedata.download`
The meat and potatoes of the DS side. It kicks off with an error code (4 bytes). If 0x01 is not zero, then it triggers `1320x`, where X is 0x01.

After this is `0x7c` bytes of padding. Then, there's a 4-byte value. This is written to the save. If this value is the same as the one in the save, then no data is downloaded.

In `dream-server`, this is treated as a CRC32 (see [Line 222 of `dsio.py`](https://github.com/NDSLink/dream-server/blob/master/dsio.py#L222)).

In Entralinked, 4 random bytes are used (see [Line 244 of `src/main/java/entralinked/network/http/pgl/PglHandler.java`](https://github.com/kuroppoi/entralinked/blob/master/src/main/java/entralinked/network/http/pgl/PglHandler.java#L244))

After that, there are 10 8-byte Pokemon (see [Line 165 of `dsio.py`](https://github.com/NDSLink/dream-server/blob/master/dsio.py#L165)).

Finally, there is the worst idea ever created by Nintendo. First, we have 20 (2 byte) item IDs, followed by (seperately!) 20 (1 byte) item quantities, so the response would be like this:
```
\x10\x10 # metal powder
\x00\x00 # ...18 more times (padding)
\x00\x01 # 1 of [downloaded item 1]
\x00\x00 # ...18 more times (padding)
```
Note (@zurgeg): what were these developers on??

Then, there's the Dream Decor catalouge.

Note (@zurgeg): Why did they offload this to the DS?

Basically, this data is a name (12 chars max, utf16-le) followed by a 1 byte index (which will be stored in the save).

Finally, there's some more data which I think kuroppoi RE'd but @zurgeg never wrote in his code. TODO: document this

