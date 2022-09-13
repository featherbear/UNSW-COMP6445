+++
date = 2022-09-13T16:25:35Z
hiddenFromHomePage = false
postMetaInFooter = false
title = "Forensic Image Formats"
[flowchartDiagrams]
enable = false
options = ""
[sequenceDiagrams]
enable = false
options = ""

+++
# Binary Dump

## dd

* Bit for bit copy of the data
* Often split into smaller file segments for ease of handling
* Can be easily mounted as a drive on Linux systems
* Many forensic tools natively support `dd` images
* Does NOT calculate the MD5 or SHA1 sum, so must be computed and stored manually

> `dd if={DEVICE} of={OUTPUT_PATH} bs=65536 conv=noerror,sync`

![](/uploads/snipaste_2022-09-14_02-25-42.jpg)

## E01 - Encase / Expert Witness Format

> See [https://github.com/libyal/libewf](https://github.com/libyal/libewf "https://github.com/libyal/libewf")

* Integrates hash calculation and case metadata
* Redundant integrity checks (both block and device level hashing)
* Can be split into smaller segments
* Native support for compression

However,

* Harder to make native commands with
* Need specialised software or libraries to create the E01

![](/uploads/snipaste_2022-09-14_02-35-01.jpg)