Sakura Wars: Columns 2 xdelta patch (Dreamcast TOSEC GDI)
============================================

Based on the [Windows patch](https://github.com/DerekPascarella/SakuraWarsColumns2-EnglishPatchDreamcast) created by Derek Pascarella.

This patch can be used on any operating system (not just Windows).

Unlike the Windows patch, which produces a unique `track03.bin` everytime you run the patcher (some entries in the GDI image are timestamped based on when you apply the patch), this patch preserves the original timestamps of the directory entries (_11/28/1999 2:57:57 PM_), it preserves the empty `DPMODEL` directory from the source image, and does not create an unused `BOOTSECTOR` directory (an artifact of old scripts for extracting & rebuilding GDI images).

