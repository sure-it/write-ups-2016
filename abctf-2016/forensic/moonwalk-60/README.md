# ABCTF 2016 : moonwalk-60

**Category:** Forensic
**Points:** 60
**Solves:** 176
**Description:**

There is something a little off about this picture. If you could help us we could give you some points! Just find us a flag!

## Write-up

$ binwalk PurpleThing.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 3200 x 2953, 8-bit/color RGBA, non-interlaced
85            0x55            Zlib compressed data, best compression, uncompressed size >= 3144
2757          0xAC5           Zlib compressed data, best compression, uncompressed size >= 3571712
765455        0xBAE0F         JPEG image data, JFIF standard  1.01
765485        0xBAE2D         TIFF image data, big-endian

$binwalk --dd=jpeg PurpleThing.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 3200 x 2953, 8-bit/color RGBA, non-interlaced
85            0x55            Zlib compressed data, best compression, uncompressed size >= 3144
2757          0xAC5           Zlib compressed data, best compression, uncompressed size >= 3571712
765455        0xBAE0F         JPEG image data, JFIF standard  1.01
765485        0xBAE2D         TIFF image data, big-endian

$ cd _PurpleThing.png.extracted/
$ eog BAE0F



## Other write-ups and resources

* [RawSec](https://rawsec.ml/en/ABCTF-60-MoonWalk-Forensics/)
