# PageTextCache.wdb

The **PageTextCache.wdb** holds information about pages which you have read (e.g. from quest items, gameobjects).


### Format:

First 4 bytes are always `WPTX` in Little-Endian order, these are filetype magic value.

Then, as with many [RIFF][link-riff]-like Blizzard file formats, there's a version field, also 4 bytes.

Finally, you get one or many entries with following structure:

| **Field Name**   | **Type**  |
| ---------------- | --------- |
| PageID           | u_i32     |
| EntryLength      | u_i32     |
| NextPageID       | u_i32     |
| PageText         | String    |


**Trivia:**
- Most (if not all) values are in [Little-Endian][link-le] order.
- `u_i32` means "Unsigned Integer, 32 bits"
- `String` is a null-terminated sequence of characters of arbitrary length.


<!-- Technical stuff -->

[link-riff]: https://en.wikipedia.org/wiki/Resource_Interchange_File_Format
[link-le]: https://en.wikipedia.org/wiki/Little-endian

<!-- Information has been aquired from https://wowdev.wiki and other private sources -->