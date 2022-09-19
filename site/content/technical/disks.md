+++
date = 2022-09-13T12:31:28Z
hiddenFromHomePage = false
postMetaInFooter = false
title = "Disks"
[flowchartDiagrams]
enable = false
options = ""
[sequenceDiagrams]
enable = false
options = ""

+++
## Physical Structure

### Hard Disk Drives

Traditional hard drives are composed of platters, which contain a number of tracks.  
Each track contains a number of blocks known as sectors (size defined by the manufacturer - originally 512B, nowadays 4096B).

We address these sectors by their [LBA](https://en.wikipedia.org/wiki/Logical_block_addressing) (logical block address), rather than by their platter-track-sector. There is also another addressing system called [CHS](Cylinder-head-sector) (cylinder-head-sector)

> **Why store things contiguous?  
> \**Reduced seek time

### Solid State Drives

SSDs use NAND flash memory rather than platters. Whilst they use the LBA addressing scheme, physical translation is handled by drivers / firmware.

SSDs scatter the data rather than writing them continguously, due to the physical limitations (lifespan) of semiconductors and silicon \[i.e. wear leveling\]

### Hidden Areas

![](/uploads/snipaste_2022-09-19_19-47-42.jpg)

![](/uploads/snipaste_2022-09-19_19-51-46.jpg)

#### Detecting HPA and DCO

![](/uploads/snipaste_2022-09-19_19-56-23.jpg)  
These tools issue ATA commands to the drive controller, rather than through the BIOS' (limited) interface

## Logical Structure

* MBR - Master Boot Record
  * Contains the volume locations and sizes
* Volumes / Partitions - Logical containers for filesystems
* Filesystem - Structure that sit within a volume
* Clusters - Grouping of sectors
* Unpartitioned space - free sectors
  * Free sectors within a volume is called **_volume slack_**

![](/uploads/snipaste_2022-09-19_19-59-32.jpg)

### The MBR

![](/uploads/snipaste_2022-09-19_20-00-55.jpg)  
The very first sector on the drive (`LBA0`).  
It contains bootstrap data (i.e. bootable), and information related to the partitions

![](/uploads/snipaste_2022-09-19_20-02-17.jpg)

![](/uploads/snipaste_2022-09-19_20-02-39.jpg)

> Note: A quick format just sets the active byte to false

### The GPT

![](/uploads/snipaste_2022-09-19_20-06-40.jpg)

![](/uploads/snipaste_2022-09-19_20-06-51.jpg)

Supersedes the MBR

Contains a "_protective MBR_" at `LBA0` to ensure older devices don't wipe the drive on connect. It will contain a single partition entry with the type code `0xEE`.

* Partition max size: 18 exabytes
* At a minimum, LBA2-34 are assigned to the partition table

![](/uploads/snipaste_2022-09-19_20-08-52.jpg)

## Unallocated / Slack / Deleted

* We can write data into unallocated areas of the disk, i.e. using a raw disk editor.
* OS APIs generally don't like writing to 'invalid' spaces on disk.
* Driver level APIs

![](/uploads/snipaste_2022-09-19_20-13-53.jpg)

### Volume Slack

Unused space between the end of a filesystem and the end of its partition

***

# Summary

Hiding techniques

* HPAs, DCOs
* Write directly to unpartitioned space
* Deleted volumes and hidden partitions
* Hiding data in volume slack

***

# What about \[...\]?

![](/uploads/snipaste_2022-09-19_20-31-32.jpg)

## Cloud

It's not just your data that's stored in a data server - privacy issues

![](/uploads/snipaste_2022-09-19_20-52-56.jpg)

## RAIDS

> RAID - "Redundant Array of Inexpensive Disks"

_'inexpensive' * cough *_

![](/uploads/snipaste_2022-09-19_20-39-21.jpg)

![](/uploads/snipaste_2022-09-19_20-39-21.jpg)

![](/uploads/snipaste_2022-09-19_20-42-06.jpg)

![](/uploads/snipaste_2022-09-19_20-43-01.jpg)

![](/uploads/snipaste_2022-09-19_20-50-05.jpg)