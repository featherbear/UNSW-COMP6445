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

> See [https://www.youtube.com/watch?v=l4IphrAjzeY](https://www.youtube.com/watch?v=l4IphrAjzeY "https://www.youtube.com/watch?v=l4IphrAjzeY")

![](/uploads/snipaste_2022-09-26_20-34-37.jpg)  
![](/uploads/snipaste_2022-09-26_20-36-08.jpg)  
![](/uploads/snipaste_2022-09-26_20-37-35.jpg)

Key notes

* $BITMAP does not track the next cluster, just the 'in-use' state

![](/uploads/snipaste_2022-09-26_20-40-09.jpg)  
Notes

* Files can actually be stored in the MFT itself - and is known as Resident Data
  * The resident data may not be fully zero'd out when it overgrows its size
  * 🔥

![](/uploads/snipaste_2022-09-26_21-23-28.jpg)

![](/uploads/snipaste_2022-09-26_20-43-49.jpg)

### Alternate Data Streams

![](/uploads/snipaste_2022-09-26_20-49-38.jpg)

### Deleted Files

![](/uploads/snipaste_2022-09-26_20-53-11.jpg)

![](/uploads/snipaste_2022-09-26_20-56-39.jpg)

***

# Slack

![](/uploads/snipaste_2022-09-26_20-59-01.jpg)

Key notes

* If you wipe unallocated space, it may not wipe the slack space that exists within allocated space

## Unallocated Clusters

![](/uploads/snipaste_2022-09-26_21-01-55.jpg)