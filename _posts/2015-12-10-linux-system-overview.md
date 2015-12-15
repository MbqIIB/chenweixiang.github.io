---
layout: post
title: "Linux System Overview"
tags: [Linux]
toc: true
---

This article introduces Linux system overview.

<!--more-->

## Linux Standard Base (LSB)

The [Linux Standard Base (LSB)](http://refspecs.linuxfoundation.org/lsb.shtml) was created to lower the overall costs of supporting the Linux platform. By reducing the differences between individual Linux distributions, the LSB greatly reduces the costs involved with porting applications to different distributions, as well as lowers the cost and effort involved in after-market support of those applications.

The picture below represents the key LSB deliverables for application and distribution developers:
![LSB Specifications and Tools](/assets/lsb_concept_tools.png)

### LSB Specifications

The official home of the LSB specification is the [Linux Foundation's Reference Specifications Archive](http://refspecs.linuxfoundation.org/lsb.shtml). The following LSB specifications are released:

* **LSB 1.0** was released on June 29, 2001.

* **LSB 1.1** was released on January 22, 2002.

* **LSB 1.2** was released on June 28, 2002.

* **LSB 1.3** was released on December 17, 2002.

* **LSB 2.0** was released on August 31, 2004. The release omitted the PPC32 and S390 architectures.

* **LSB 2.0.1** was released on October 21, 2004.

* **LSB 2.1** was released on March 11, 2005.

* **LSB 3.0** was released on July 6, 2005.

* **LSB 3.1** Core was released on October 27, 2005; LSB 3.1 C++ and Desktop were released April 24, 2006.

    Note that the Core module specification of LSB 3.1 is the document submitted for publication by ISO/IEC as **IS 23360:1996**. The following are the main parts of it and can be downloaded from [Publicly Available Standards](http://standards.iso.org/ittf/PubliclyAvailableStandards/index.html):
    
    ISO/IEC 23360-1:2006 Linux Standard Base (LSB) core specification 3.1 – Part 1: Generic specification
    ISO/IEC 23360-2:2006 Linux Standard Base (LSB) core specification 3.1 – Part 2: Specification for IA-32 architecture
    ISO/IEC 23360-3:2006 Linux Standard Base (LSB) core specification 3.1 – Part 3: Specification for IA-64 architecture
    ISO/IEC 23360-4:2006 Linux Standard Base (LSB) core specification 3.1 – Part 4: Specification for AMD64 architecture
    ISO/IEC 23360-5:2006 Linux Standard Base (LSB) core specification 3.1 – Part 5: Specification for PPC32 architecture
    ISO/IEC 23360-6:2006 Linux Standard Base (LSB) core specification 3.1 – Part 6: Specification for PPC64 architecture
    ISO/IEC 23360-7:2006 Linux Standard Base (LSB) core specification 3.1 – Part 7: Specification for S390 architecture
    ISO/IEC 23360-8:2006 Linux Standard Base (LSB) core specification 3.1 – Part 8: Specification for S390X architecture

    There is also [ISO/IEC TR 24715:2006](http://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=38825) which identifies areas of conflict between ISO/IEC 23360 (the Linux Standard Base 3.1 specification) and the ISO/IEC 9945:2003 (POSIX) International Standard.

* **LSB 3.2** was released on January 25, 2008

    Note that the LSB 3.2 Core specification is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

* **LSB 4.0** was released on May 1, 2009

    Note that the LSB 4.0 Core specification is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

* **LSB 4.1** was released on February 16, 2011

    Note that the LSB 4.1 Core specification is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

* **LSB 5.0** was released on June 3, 2015.

    Note that the LSB 5.0 Core specification set is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

The Linux Standard Base (LSB) specifications are made available in two parts: **an architecture independent (generic) part** and **an architecture dependent part**. For LSB 4.1, the architecture independent part is comprised of five modules: **Core**, **C++**, **Desktop**, **Runtime Languages** and **Printing**. The architecture dependent part is comprised of three modules: **Core**, **C++** and **Desktop**. For LSB 5.0, the architecture independent part is comprised of five modules: **Common**, **Core**, **Desktop**, **Runtime Languages** and **Imaging**. The architecture dependent part is comprised of three modules: **Core** and **Desktop**.

Also, there are **mandatory** and **trial use** modules in the specification. The former impose mandatory requirements on LSB compliant distributions and applications may safely rely on the functionality described in mandatory modules. Functionality in trial use modules is not required in LSB compliant distributions and applications should take this into consideration. Meanwhile, trial use modules represent candidates for inclusion in the next versions of LSB.

### LSB Navigator

LSB Database is a central place for storing information about the LSB standard and about the surrounding Linux ecosystem. [LSB Navigator](http://www.linuxbase.org/navigator/commons/welcome.php) represents web based interface over all these information. It can be used by Linux developers, Linux distribution vendors and LSB workgroup to browse, query, analyze and submit various information.

### LSB Certification

Refer to [LSB Certification](https://www.linuxbase.org/lsb-cert/welcome_cert.php) for detail information about LSB certification. In that website, you can track the industry picture of LSB certification in **Product Directory** area. For instance, a list of Linux distributions and applications certified for compliance with the LSB standard can be found [here](https://www.linuxbase.org/lsb-cert/productdir.php?by_prod).

## Filesystem Hierarchy Standard (FHS)

The [Filesystem Hierarchy Standard (FHS)](http://www.linuxfoundation.org/collaborate/workgroups/lsb/fhs) defines the directory structure and directory contents in Unix and Unix-like operating systems. It is maintained by the Linux Foundation. Currently it is only used by Linux distributions. And the Linux Standard Base (LSB) refers to it as a standard.

[Filesystem Hierarchy Standard Specifications Archive](http://refspecs.linuxfoundation.org/fhs.shtml)

### History of FHS

FHS releases the following versions, which can be downloaded from [here](http://www.ibiblio.org/pub/Linux/docs/fsstnd/old/fsstnd-1.0/) for FHS 1.0, and [Filesystem Hierarchy Standard Specifications Archive](http://refspecs.linuxfoundation.org/fhs.shtml) for FHS 2.3 and beyond.

| Version | Release Date | Notes |
| :-----: | :----------: | :---- |
| 1.0     | 1994-02-14   | FSSTND (**F**ile**S**ystem **ST**a**ND**ard) |
| 1.1     | 1994-10-09   | FSSTND (**F**ile**S**ystem **ST**a**ND**ard) |
| 1.2     | 1995-03-28   | FSSTND (**F**ile**S**ystem **ST**a**ND**ard) |
| 2.0     | 1997-10-26   | FHS 2.0 is the direct successor for FSSTND 1.2. Name changed from FSSTND to FHS. |
| 2.1     | 2000-04-12   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |
| 2.2     | 2001-05-23   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |
| 2.3     | 2004-01-29   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |
| 3.0     | 2015-05-18   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |

### FHS 3.0 Directory Structure

| Directory | Requirement | Description |
| :-------- | :---------: | :---------- |
| **```/```** | **Required** | **Primary hierarchy** root directory. |
| **```/bin```** | **Required** | Essential command binaries (for use by all users). Must be no subdirectories in ```/bin```. |
| **```/boot```** | **Required** | Static files of the boot loader. |
| **```/dev```** | **Required** | Device files. |
| **```/etc```** | **Required** | Host-specific system configuration. |
| ```/etc/opt``` | **Required** | Configuration files for add-on packages that are stored in ```/opt/```. |
| ```/etc/X11``` | Optional | Configuration for the X Window system. |
| ```/etc/sgml``` | Optional | Configuration for SGML. |
| ```/etc/xml``` | Optional | Configuration for XML. |
| **```/home```** | Optional | User home directories. |
| **```/lib```** | **Required** | Essential shared libraries and kernel modules. |
| ```/lib/modules``` | Optional | Loadable kernel modules. |
| ```/lib<qual>``` | Optional | Alternate format essential shared libraries. |
| **```/media```** | **Required** | Mount point for removable media (appeared in FHS 2.3). |
| ```/media/floppy``` | Optional | Floppy drive. |
| ```/media/cdrom``` | Optional | CD-ROM drive. |
| ```/media/cdrecorder``` | Optional | CD writer. |
| ```/media/zip``` | Optional | Zip drive. |
| **```/mnt```** | **Required** |  Mount point for a temporarily mounted filesystem. |
| **```/opt```** | **Required** | Add-on application software packages. |
| **```/proc```** | ***De-facto*** | Virtual filesystem providing process and kernel information as files. |
| **```/root```** | Optional | Home directory for the root user. |
| **```/run```** | **Required** | Data relevant to running processes. |
| **```/sbin```** | **Required** | Essential system binaries, e.g., fsck, init, route. |
| **```/srv```** | **Required** | Data for services provided by this system. |
| **```/tmp```** | **Required** | Temporary files. Often not preserved between system reboots, see ```/var/tmp```. |
| **```/usr```** | **Required** | **Secondary hierarchy** for read-only user data. |
| ```/usr/bin``` | **Required** | Non-essential command binaries. |
| ```/usr/games``` | Optional | Games and educational binaries. |
| ```/usr/include``` | Optional | Header files included by C programs. |
| ```/usr/include/bsd``` | Optional | BSD compatibility include files. |
| ```/usr/lib``` | **Required** | Libraries for the binaries in ```/usr/bin/``` and ```/usr/sbin/```. |
| ```/usr/libexec``` | Optional | Binaries run by other programs. |
| ```/usr/lib<qual>``` | Optional | Alternate format libraries. |
| **```/usr/local```** | **Required** | **Tertiary hierarchy** for local data, specific to this host. |
| ```/usr/local/bin``` | **Required** | Local binaries. |
| ```/usr/local/etc``` | **Required** | Host-specific system configuration for local binaries. |
| ```/usr/local/games``` | **Required** | Local game binaries. |
| ```/usr/local/include``` | **Required** | Local C header files. |
| ```/usr/local/lib``` | **Required** | Local libraries. |
| ```/usr/local/lib<qual>``` | Optional | Exist only if ```/lib<qual>``` or ```/usr/lib<qual>``` exist. |
| ```/usr/local/man``` | **Required** | Local online manuals. |
| ```/usr/local/sbin``` | **Required** | Local system binaries. |
| ```/usr/local/share``` | **Required** | Local architecture-independent hierarchy. |
| ```/usr/local/src``` | **Required** | Local source code. |
| ```/usr/sbin``` | **Required** | Non-essential standard system binaries. |
| ```/usr/share``` | **Required** | Architecture-independent (shared) data. |
| ```/usr/share/color``` | Optional | Color management information. |
| ```/usr/share/color/icc``` | Optional | ICC color profiles. |
| ```/usr/share/dict``` | Optional | Word lists. |
| ```/usr/share/dict/words``` | Optional | List of English words. |
| ```/usr/share/doc``` | Optional | Miscellaneous documentation. |
| ```/usr/share/games``` | Optional | Static data files for ```/usr/games```. |
| ```/usr/share/info``` | Optional | Primary directory for GNU Info system. |
| ```/usr/share/locale``` | Optional | Locale information. |
| ```/usr/share/man``` | **Required** | Manual pages. |
| ```/usr/share/man/man1``` | Optional | User programs. |
| ```/usr/share/man/man2``` | Optional | System calls. |
| ```/usr/share/man/man3``` | Optional | Library calls. |
| ```/usr/share/man/man4``` | Optional | Special files. |
| ```/usr/share/man/man5``` | Optional | File formats. |
| ```/usr/share/man/man6``` | Optional | Games. |
| ```/usr/share/man/man7``` | Optional | Miscellaneous. |
| ```/usr/share/man/man8``` | Optional | System administration. |
| ```/usr/share/misc``` | **Required** | Miscellaneous architecture-independent data. |
| ```/usr/share/misc/ascii``` | Optional | ASCII character set table. |
| ```/usr/share/misc/termcap``` | Optional | Terminal capability database. |
| ```/usr/share/misc/termcap.db``` | Optional | Terminal capability database. |
| ```/usr/share/nls``` | Optional | Message catalogs for Native language support. |
| ```/usr/share/ppd``` | Optional | Printer definitions. |
| ```/usr/share/sgml``` | Optional | SGML data. |
| ```/usr/share/sgml/docbook``` | Optional | docbook DTD. |
| ```/usr/share/sgml/tei``` | Optional | tei DTD. |
| ```/usr/share/sgml/html``` | Optional | html DTD. |
| ```/usr/share/sgml/mathml``` | Optional | mathml DTD. |
| ```/usr/share/terminfo``` | Optional | Directories for terminfo database. |
| ```/usr/share/tmac``` | Optional | troff macros not distributed with groff. |
| ```/usr/share/xml``` | Optional | XML data. |
| ```/usr/share/xml/docbook``` | Optional | docbook XML DTD. |
| ```/usr/share/xml/xhtml``` | Optional | XHTML DTD. |
| ```/usr/share/xml/mathml``` | Optional | MathML DTD. |
| ```/usr/share/zoneinfo``` | Optional | Timezone information and configuration. |
| ```/usr/src``` | Optional | Source code, e.g., kernel source code with its header files. |
| ```/usr/X11R6``` | Optional | X Window System, Version 11, Release 6 (up to FHS-2.3). |
| **```/var```** | **Required** | Variable files. |
| ```/var/account``` | Optional | Process accounting logs. |
| ```/var/account/fonts``` | Optional | Locally-generated fonts. |
| ```/var/account/man``` | Optional | Locally-formatted manual pages. |
| ```/var/account/www``` | Optional | WWW proxy or cache data. |
| ```/var/account/<package>``` | Optional | Package specific cache data. |
| ```/var/cache``` | **Required** | Application cache data.  |
| ```/var/cache/fonts``` | Optional | Locally-generated fonts. |
| ```/var/cache/man``` | Optional | Locally-formatted manual pages. |
| ```/var/crash``` | Optional | System crash dumps. |
| ```/var/games``` | Optional | Variable game data. |
| ```/var/lib``` | **Required** | Variable state information. |
| ```/var/lib/<editor>``` | Optional | Editor backup files and state. |
| ```/var/lib/<pkgtool>``` | Optional | Packaging support files. |
| ```/var/lib/<package>``` | Optional | State data for packages and subsystems. |
| ```/var/lib/color``` | Optional | Color management information. |
| ```/var/lib/hwclock``` | Optional | State directory for hwclock. |
| ```/var/lib/misc``` | **Required** | Miscellaneous variable data. |
| ```/var/lib/xdm``` | Optional | X display manager variable data. |
| ```/var/local``` | **Required** | Variable data for ```/usr/local```. |
| ```/var/lock``` | **Required** | Lock files. Files keeping track of resources currently in use. |
| ```/var/log``` | **Required** | Log files and directories. |
| ```/var/log/lastlog``` | **Required** | Record of last login of each user. |
| ```/var/log/messages``` | **Required** | System messages from syslogd. |
| ```/var/log/wtmp``` | **Required** | Record of all logins and logouts. |
| ```/var/mail``` | Optional | User mailbox files. |
| ```/var/opt``` | **Required** | Variable data from add-on packages that are stored in ```/opt/```. |
| ```/var/run``` | **Required** | Data relevant to running processes. |
| ```/var/spool``` | **Required** | Application spool data. |
| ```/var/spool/lpd``` | Optional | Printer spool directory. |
| ```/var/spool/mqueue``` | Optional | Outgoing mail queue. |
| ```/var/spool/news``` | Optional | News spool directory. |
| ```/var/spool/rwho``` | Optional | Rwhod files. |
| ```/var/spool/uucp``` | Optional | Spool directory for UUCP. |
| ```/var/tmp``` | **Required** | Temporary files to be preserved between reboots.|
| ```/var/yp``` | Optional | Network Information Service (NIS) database files. |

## Linux kernel Releases

The Linux kernel is the most important part of the Linux system. You can get Linux kernel source code from its official site [The Linux Kernel Archives](https://www.kernel.org/). [Here](https://en.wikipedia.org/wiki/History_of_Linux) is a short history of Linux kernel:

| kernel version | Release date |  Status  |
| :------------: | :----------: | :------: |
| 0.01           | Sep 17, 1991 |          |
| 0.10           | Nov 1991     |          |
| 0.95           | Mar 08, 1992 |          |
| 1.0            | Mar 14, 1994 |          |
| 1.1            | Apr 06, 1994 |          |
| 1.2            | Mar 07, 1995 |          |
| 1.3            | Jun 12, 1995 |          |
| pre2.0         | May 12, 1996 |          |
| 2.0            | Jun 09, 1996 |          |
| 2.2            | Jan 26, 1999 |          |
| 2.4            | Jan 04, 2001 |          |
| 2.6            | Dec 17, 2003 |          |
| 2.6.11         | Mar 02, 2005 |          |
| 2.6.12         | Jun 18, 2005 |          |
| 2.6.13         | Aug 28, 2005 |          |
| 2.6.14         | Oct 27, 2005 |          |
| 2.6.15         | Jan 02, 2006 |          |
| 2.6.16         | Mar 20, 2006 |          |
| 2.6.17         | Jun 17, 2006 |          |
| 2.6.18         | Sep 20, 2006 |          |
| 2.6.19         | Nov 26, 2006 |          |
| 2.6.20         | Feb 04, 2007 |          |
| 2.6.21         | Apr 25, 2007 |          |
| 2.6.22         | Jul 08, 2007 |          |
| 2.6.23         | Oct 09, 2007 |          |
| 2.6.24         | Jan 24, 2008 |          |
| 2.6.25         | Apr 16, 2008 |          |
| 2.6.26         | Jul 13, 2008 |          |
| 2.6.27         | Oct 09, 2008 |          |
| 2.6.28         | Dec 12, 2008 |          |
| 2.6.29         | Mar 23, 2009 |          |
| 2.6.30         | Jun 09, 2009 |          |
| 2.6.31         | Sep 09, 2009 |          |
| 2.6.32         | Dec 02, 2009 | longterm |
| 2.6.33         | Feb 24, 2010 |          |
| 2.6.34         | May 16, 2010 |          |
| 2.6.35         | Aug 01, 2010 |          |
| 2.6.36         | Oct 20, 2010 |          |
| 2.6.37         | Jan 04, 2011 |          |
| 2.6.38         | Mar 14, 2011 |          |
| 2.6.39         | May 18, 2011 |          |
| 3.0            | Jul 21, 2011 |          |
| 3.1            | Oct 24, 2011 |          |
| 3.2            | Jan 04, 2012 | longterm |
| 3.3            | Mar 18, 2012 |          |
| 3.4            | May 20, 2012 | longterm |
| 3.5            | Jul 21, 2012 |          |
| 3.6            | Sep 30, 2012 |          |
| 3.7            | Dec 10, 2012 |          |
| 3.8            | Feb 18, 2013 |          |
| 3.9            | Apr 28, 2013 |          |
| 3.10           | Jun 30, 2013 | longterm |
| 3.11           | Sep 02, 2013 |          |
| 3.12           | Nov 03, 2013 | longterm |
| 3.13           | Jan 19, 2014 |          |
| 3.14           | Mar 30, 2014 | longterm |
| 3.15           | Jun 08, 2014 |          |
| 3.16           | Aug 03, 2014 |          |
| 3.17           | Oct 05, 2014 |          |
| 3.18           | Dec 07, 2014 | longterm |
| 3.19           | Feb 08, 2015 |          |
| 4.0            | Apr 12, 2015 |          |
| 4.1            | Jun 22, 2015 | longterm |
| 4.2            | Aug 30, 2015 | stable   |
| 4.3            | Nov 01, 2015 | stable   |
| 4.4            | Dec 06, 2015 | mainline |

<br>

If we draw a picture of Linux kernel releases, it should be like this:

![Linux_Kernel_Releases](/assets/Linux_Kernel_Releases_20151114_without_linux-next.svg)

![Linux_Kernel_Timeline](/assets/linux_kernel_timeline.png)

### Version Numbering

The Linux kernel has had [three different numbering schemes](https://en.wikipedia.org/wiki/Linux_kernel#Version_numbering):

* First numbering scheme: **kernel 0.01 ~ 1.0**

    The first scheme was used in the run-up to "1.0". The first version of the kernel was 0.01. This was followed by 0.02, 0.03, 0.10, 0.11, 0.12 (the first GPL version), 0.95, 0.96, 0.97, 0.98, 0.99 and then 1.0. From 0.95 on there were many patch releases between versions.

* Second numbering scheme: **kernel 1.0 ~ 2.6.0**, Even-odd version numbering scheme

    After the 1.0 release and prior to version 2.6, the number was composed as "x.y.z", where the number "x" denoted the kernel version, the number "y" denoted the major revision of the kernel, and the number "z" indicated the minor revision of the kernel. The kernel version was changed only when major changes in the code and the concept of the kernel occurred (Note: version 3.0 was released in 2011, but it was not a major change in kernel concept). The major revision was assigned according to the **even-odd version numbering scheme**. The minor revision had been changed whenever security patches, bug fixes, new features or drivers were implemented in the kernel.

* Third numbering scheme: **kernel 2.6.0 ~ present**, Time-based release numbering scheme

    After version 2.6.0 was released in 2004, a "time-based" release cycle was adopted. For about seven years, the first two numbers remained "2.6", and the third number was incremented with each new release, which rolled out after two to three months. A fourth number was sometimes added to account for bug and security fixes (only) to the kernel version. The even-odd system of alternation between stable and unstable was gone. Instead, development pre-releases are titled release candidates, which is indicated by appending the suffix '-rc' to the kernel version, followed by an ordinal number.

    The first use of the fourth number occurred when a grave error, which required immediate fixing, was encountered in 2.6.8's NFS code. However, there were not enough other changes to legitimize the release of a new minor revision (which would have been 2.6.9). So, [2.6.8.1 was released](https://lwn.net/Articles/97898/), with the [only change](https://www.kernel.org/pub/linux/kernel/v2.6/ChangeLog-2.6.8.1) being the fix of that error. With 2.6.11, this was adopted as the new official versioning policy. Later it became customary to continuously back-port major bug-fixes and security patches to released kernels and indicate that by updating the fourth number.

    On 29 May 2011, Linus Torvalds [announced](https://lkml.org/lkml/2011/5/29/204) that the kernel version would be bumped to 3.0 for the release following 2.6.39, **due to the minor version number getting too large and to commemorate the 20th anniversary of Linux**. It continued the time-based release practice introduced with 2.6.0, but using the second number; for example, 3.1 would follow 3.0 after a few months.

    The major version number was also raised to 4 [announced on 22 Feb 2015](https://lkml.org/lkml/2015/2/22/203), for the release following version 3.19.

## Linux Distributions

### GNU/Linux Distribution Timeline

[GNU/Linux Distribution Timeline](http://futurist.se/gldt/) is a cladogram of GNU/Linux distributions, placed on a timeline. The project started in 2006 and currently lists almost 500 distributions. The following figure is GNU/Linux Distribution Timeline 12.10, you will get more detail information when you open the figure and click the name of specific distribution.

![GNU/Linux Distribution Timeline 12.10](/assets/GNU_Linux_Distribution_Timeline_12.10.svg)

### DistroWatch.com

If you want to know all information for all of those different linux distributions in one place, the website [DistroWatch](http://distrowatch.com/) is what you need.

## Reference

[The Linux Kernel Archives](https://www.kernel.org/)

[Linux kernel version numbering](https://en.wikipedia.org/wiki/Linux_kernel#Version_numbering)

[Linux Foundation Referenced Specifications](http://refspecs.linuxfoundation.org/)