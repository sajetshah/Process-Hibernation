Process-Hibernation
===================
Objective:

The basic idea is to freeze a running process in Linux operating system and resume it
from the same point and thus providing support for network processes.
We have taken help of Cryopid, an open source software for this purpose.

Challenging Part:

The most challenging task was to get the data of all the sections that the
process was using and storing them in an executable file. The data collected has to be
stored sequentially so that while resuming there are no segmentation faults and the
process gets resumed successfully from the same point.

Steps to Freeze a process:

1) extract and go to src folder ( type 1)rm arch   then  2)ln -s arch-i386 arch on terminal  )

2) try make

3) if error make: arch command not found   (in case of zlib.h file not found , download zlib-1.2.3.tar.gz file , extract the  file and do     1)./configure    then  2)make      and      then            3)sudo make install          on it.)

4) then it is because util-linux does not contain arch command in latest version instead there is uname -m command.

5) type uname -m on terminal (output willbe i686 0r i386)

6) then open the makefile and  change statement ARCH= $(shell arch)  to ARCH= i686

7)make

8) see if freeze.exe is created

Team Members:
Tejas Shah
Aniket Pansare
Hitesh Oswal
Rathish R
