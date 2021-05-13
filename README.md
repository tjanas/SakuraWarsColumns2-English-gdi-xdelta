Sakura Wars: Columns 2 xdelta patch (Dreamcast TOSEC GDI)
============================================

Based on the [Windows patch](https://github.com/DerekPascarella/SakuraWarsColumns2-EnglishPatchDreamcast) created by Derek Pascarella.

This patch can be used on any operating system (not just Windows).

Unlike the Windows patch, which produces a unique `track03.bin` everytime you run the patcher (some entries in the GDI image are timestamped based on when you apply the patch), this patch preserves the original timestamps of the directory entries (_11/28/1999 2:57:57 PM_), it preserves the empty `DPMODEL` directory from the source image, and does not create an unused `BOOTSECTOR` directory (an artifact of old scripts for extracting & rebuilding GDI images).

Apply the included xdelta patch to `track03.bin` from `Hanagumi Taisen Columns 2 v1.000 (1999)(Sega)(JP)[!]` in the TOSEC GDI set:

```
Source:
Name: track03.bin
Size: 1185760800 bytes
CRC32: 07BBFE5B
SHA256: 6490D2A6CE3A39ABC28D2D6686AA96B6F066AB6FE6DB092AEF18663F74AD2FB2
SHA1: 124FCD001B835B0AFFBF5B3EBC2A9E87978EE4AA
MD5: 4CA5E50E56E64F11BE0FAEB6FC447877

Modified:
Name: track03.bin
Size: 1185760800 bytes
CRC32: BC8ECE42
SHA256: 3CFD372371151E6BBA70466D58043B8B1098B44996351A2CDF7017C49A62A867
SHA1: 6D301DBC296AE6C2C5650164C00AE330DF69D24A
MD5: 1DEAF1058AC6019140043BFDCD56FF13
```
