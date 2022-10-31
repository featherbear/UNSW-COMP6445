+++
date = 2022-10-31T08:23:29Z
draft = true
hiddenFromHomePage = false
postMetaInFooter = false
title = "Memory Forensics"
[flowchartDiagrams]
enable = false
options = ""
[sequenceDiagrams]
enable = false
options = ""

+++
> You can hide, but you have to run

***

An attacker can do many things to disguise or even hide their malware and tools on disk to avoid detection.

* Renaming / Moving
* Packing
* Encrypting
* Rootkits

Eventually, the code has to reveal itself when it executes in memory. In the case of remote access, the software has to continue to execute to be able to receive commands and keep a foothold in the system.

***

# Memory is volatile, in normal cases

* Physical forensics
* Hibernation file

***

# Capture Tools

* FTK Imager
* Redline Collector
* dd / windd
* Powershell
* Task Manager

# Tools

* [Volatility](https://www.volatilityfoundation.org/) (also see [autoVolatility](https://github.com/carlospolop/autoVolatility))
* [Rekall](http://www.rekall-forensic.com/) 

***

# Analysis Approach

![](/uploads/snipaste_2022-10-31_19-48-50.jpg)  
![](/uploads/snipaste_2022-10-31_19-52-44.jpg)  
![](/uploads/snipaste_2022-10-31_19-54-15.jpg)  
![](/uploads/snipaste_2022-10-31_19-55-04.jpg)  
![](/uploads/snipaste_2022-10-31_19-58-53.jpg)  
![](/uploads/snipaste_2022-10-31_20-00-20.jpg)  
![](/uploads/snipaste_2022-10-31_20-00-56.jpg)  
![](/uploads/snipaste_2022-10-31_20-04-23.jpg)  
![](/uploads/snipaste_2022-10-31_20-06-04.jpg)

***

# Redline

![](/uploads/snipaste_2022-10-31_20-07-20.jpg)