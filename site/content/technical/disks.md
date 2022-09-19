+++
date = 2022-09-13T12:31:28Z
draft = true
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
> **Reduced seek time

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
  * Free space sectors between volumes is called **_volume slack_**

![](/uploads/snipaste_2022-09-19_19-59-32.jpg)

### The MBR

## Unallocated / Slack / Deleted

## Complex Structures

## 