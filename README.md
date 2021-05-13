Sakura Wars: Columns 2 xdelta patch (Dreamcast TOSEC GDI)
============================================

Based on the [Windows patch](https://github.com/DerekPascarella/SakuraWarsColumns2-EnglishPatchDreamcast) created by Derek Pascarella.

This patch can be used on any operating system (not just Windows).

Unlike the Windows patch, which produces a unique `track03.bin` everytime you run the patcher (some entries in the GDI image are timestamped based on when you apply the patch), this patch preserves the original timestamps of the directory entries (_11/28/1999 2:57:57 PM_), it preserves the empty `DPMODEL` directory from the source image, and does not create an unused `BOOTSECTOR` directory (an artifact of old scripts for extracting & rebuilding GDI images). I [manually altered](https://www.nirsoft.net/utils/bulk_file_changer.html) the timestamp of the original extracted directories so they continued to have the same value from the source image, and built a [newer fork](https://github.com/Sappharad/GDIbuilder/tree/master/buildgdi) of [buildgdi](https://github.com/tjanas/SakuraWarsColumns2-English-gdi-xdelta/raw/extract_and_rebuild_tools/extract_and_rebuild_tools.7z) to preserve these timestamps and re-add the [empty directory](https://sourceforge.net/p/dcisotools/code/ci/5f14737ba6152592d9ed7ef09d074822db71650c/).

I also reverted these volume timestamp bytes at offset 0x9630 to preserve the original "1999112905575700" values (otherwise they are based on when the gdi is rebuilt):
```
20 20 20 20 20 20 20 20 20 20 20 20 20 31 39 39
39 31 31 32 39 30 35 35 37 35 37 30 30 24 31 39
39 39 31 31 32 39 30 35 35 37 35 37 30 30 24 30
30 30 30 30 30 30 30 30 30 30 30 30 30 30 30 00
30 30 30 30 30 30 30 30 30 30 30 30 30 30 30 30
```

Download these three multipart 7z archives (total size is 55.7MB):  
[Sakura Wars - Columns 2 (J) T+Eng v1.1 ateam (TOSEC GDI patch).7z.001](https://github.com/tjanas/SakuraWarsColumns2-English-gdi-xdelta/raw/main/Sakura%20Wars%20-%20Columns%202%20(J)%20T%2BEng%20v1.1%20ateam%20(TOSEC%20GDI%20patch).7z.001)  
[Sakura Wars - Columns 2 (J) T+Eng v1.1 ateam (TOSEC GDI patch).7z.002](https://github.com/tjanas/SakuraWarsColumns2-English-gdi-xdelta/raw/main/Sakura%20Wars%20-%20Columns%202%20(J)%20T%2BEng%20v1.1%20ateam%20(TOSEC%20GDI%20patch).7z.002)  
[Sakura Wars - Columns 2 (J) T+Eng v1.1 ateam (TOSEC GDI patch).7z.003](https://github.com/tjanas/SakuraWarsColumns2-English-gdi-xdelta/raw/main/Sakura%20Wars%20-%20Columns%202%20(J)%20T%2BEng%20v1.1%20ateam%20(TOSEC%20GDI%20patch).7z.003)  

After extracting the 7z archive, apply the included xdelta patch to `track03.bin` from `Hanagumi Taisen Columns 2 v1.000 (1999)(Sega)(JP)[!]` in the [TOSEC](https://www.tosecdev.org/) GDI set:

```
<game name="Hanagumi Taisen Columns 2 v1.000 (1999)(Sega)(JP)[!]">
	<description>Hanagumi Taisen Columns 2 v1.000 (1999)(Sega)(JP)[!]</description>
	<rom name="Hanagumi Taisen Columns 2 v1.000 (1999)(Sega)(JP)[!].gdi" size="87" crc="468c1495" sha1="980036e44ad9d694ea1699cd05c86ccd0c894c47" md5="346fea58ab1a55c577138c5b04319157"/>
	<rom name="track01.bin" size="1058400" crc="5504d937" sha1="6c047d255475f0a2f69750ccf99fcd5d300ee03b" md5="bc9705193d44fe615854e9ade6089e26"/>
	<rom name="track02.raw" size="14652960" crc="03fb25fd" sha1="7051a0791bc11feb1e0fd737366e204de63312c8" md5="98d912d36b179dc5d2386e41b72ffbc9"/>
	<rom name="track03.bin" size="1185760800" crc="07bbfe5b" sha1="124fcd001b835b0affbf5b3ebc2a9e87978ee4aa" md5="4ca5e50e56e64f11be0faeb6fc447877"/>
</game>
```

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
CRC32: 5EA441A4
SHA256: FE99A761131B57FA60C8441AA4150D8B0AEB59DD75E111AF31A15AA72AEFB294
SHA1: 105B6FCFD2E6A73675BDFC99F95FD18A70A318B9
MD5: 0AF66099DC142572357F780A3612AE4F
```
