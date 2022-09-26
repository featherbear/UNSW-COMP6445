+++
date = 2022-09-13T12:32:14Z
draft = true
hiddenFromHomePage = false
postMetaInFooter = false
title = "Filesystems"
[flowchartDiagrams]
enable = false
options = ""
[sequenceDiagrams]
enable = false
options = ""

+++
> See [Disks](../disks)
>
> Also see [COMP3231/file-systems](https://featherbear.cc/UNSW-COMP3231/post/file-systems/)

***

## FAT32

![](/uploads/snipaste_2022-09-26_20-07-24.jpg)

### Boot Record

Always located on the first sector

![](/uploads/snipaste_2022-09-26_20-11-00.jpg)

### File Allocation Table

![](/uploads/snipaste_2022-09-26_20-18-25.jpg)

#### Example

![](/uploads/snipaste_2022-09-26_20-19-04.jpg)  
![](/uploads/snipaste_2022-09-26_20-20-57.jpg)

Two redundant tables

### Directory Entries and Data

![](/uploads/snipaste_2022-09-26_20-12-44.jpg)

![](/uploads/snipaste_2022-09-26_20-15-24.jpg)

### Deleted Files

![](/uploads/snipaste_2022-09-26_20-22-52.jpg)

***

## NTFS