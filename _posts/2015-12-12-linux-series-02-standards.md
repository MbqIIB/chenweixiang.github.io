---
layout: post
title: "Linux Series #2: Linux Standards"
tags: [Linux]
toc: true
---

This article introduces standards related to Linux: Filesystem Hierarchy Standard (FHS) and Linux Standard Base (LSB).

<!--more-->

# Filesystem Hierarchy Standard (FHS)

The [Filesystem Hierarchy Standard (FHS)](http://www.linuxfoundation.org/collaborate/workgroups/lsb/fhs) defines the directory structure and directory contents in Unix and Unix-like operating systems. It is maintained by the [Linux Foundation](http://www.linuxfoundation.org/). [This page](http://www.pathname.com/fhs/) is the home of the Filesystem Hierarchy Standard (FHS). Currently, it is only used by Linux distributions. And the [Linux Standard Base (LSB)](http://refspecs.linuxfoundation.org/lsb.shtml) refers to it as a standard, see section *VI. Execution Environment 16. File System Hierarchy* in [Linux Standard Base (LSB) Core Specification 3.1](http://refspecs.linuxfoundation.org/LSB_3.1.0/LSB-Core-generic/LSB-Core-generic/execenvfhs.html).

## History of FHS

FHS releases the following versions, which can be downloaded from [here](http://www.ibiblio.org/pub/Linux/docs/fsstnd/old/fsstnd-1.0/) for FHS 1.0, and from [Filesystem Hierarchy Standard Specifications Archive](http://refspecs.linuxfoundation.org/fhs.shtml) for FHS 2.3 and beyond.

| Version | Release Date | Notes |
| :-----: | :----------: | :---- |
| 1.0     | 1994-02-14   | FSSTND (**F**ile**S**ystem **ST**a**ND**ard) |
| 1.1     | 1994-10-09   | FSSTND (**F**ile**S**ystem **ST**a**ND**ard) |
| 1.2     | 1995-03-28   | FSSTND (**F**ile**S**ystem **ST**a**ND**ard) |
| 2.0     | 1997-10-26   | FHS 2.0 is the direct successor for FSSTND 1.2. Name changed from FSSTND to FHS. |
| 2.1     | 2000-04-12   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |
| 2.2     | 2001-05-23   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |
| **2.3** | 2004-01-29   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |
| **3.0** | 2015-05-18   | FHS (**F**ilesystem **H**ierarchy **S**tandard) |

## Directory Structure defined in FHS 3.0

The following table contains the directory structures defined in FHS 3.0. For more detail explanations and the files contained in the directories, refer to [FHS 3.0](http://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html).

| Directory | Requirement | Description |
| :-------- | :---------: | :---------- |
| **```/```** | **Required** | **Primary hierarchy** root directory. |
| **```/bin```** | **Required** | Essential command binaries (for use by all users). Must be no subdirectories in ```/bin```. |
| **```/boot```** | **Required** | Static files of the boot loader. |
| **```/dev```** | **Required** | Device files. |
| ```/dev/null``` | ***Required*** | **Required for Linux**. All data written to this device is discarded. A read from this device will return an EOF condition. |
| ```/dev/zero``` | ***Required*** | **Required for Linux**. This device is a source of zeroed out data. All data written to this device is discarded. A read from this device will return as many bytes containing the value zero as was requested. |
| ```/dev/tty``` | ***Required*** | **Required for Linux**. This device is a synonym for the controlling terminal of a process. Once this device is opened, all reads and writes will behave as if the actual controlling terminal device had been opened. |
| **```/etc```** | **Required** | Host-specific system configuration. Recommended that configuration files are stored in subdirectories of ```/etc``` rather than directly in ```/etc```. |
| ```/etc/opt``` | **Required** | Configuration files for add-on software packages that are stored in ```/opt```. |
| ```/etc/X11``` | Optional | Configuration for the X Window system. |
| ```/etc/sgml``` | Optional | Configuration for SGML. |
| ```/etc/xml``` | Optional | Configuration for XML. |
| **```/home```** | Optional | User home directories. User configuration files are ```~/.<file>``` or ```~/.<subdir>/<files>``` |
| **```/lib```** | **Required** | Essential shared libraries and kernel modules. |
| ```/lib/modules``` | Optional | Loadable kernel modules. |
| ```/lib<qual>``` | Optional | Alternate format essential shared libraries. |
| **```/media```** | **Required** | Mount point for removable media (appeared in **FHS 2.3**), which contains subdirectories for different removable medias. |
| ```/media/cdrom``` | Optional | CD-ROM drive. |
| ```/media/cdrecorder``` | Optional | CD writer. |
| ```/media/floppy``` | Optional | Floppy drive. |
| ```/media/zip``` | Optional | Zip drive. |
| **```/mnt```** | **Required** |  Mount point for a temporarily mounted filesystem. |
| **```/opt```** | **Required** | Add-on application software packages. A package to be installed in ```/opt``` must locate its static files in a separate directory ```/opt/<package>``` or ```/opt/<provider>```. |
| ```/opt/<package>``` | Optional | Static package objects. |
| ```/opt/<package>/bin``` | Optional | Binaries of the software package. |
| ```/opt/<package>/share/man``` | Optional | UNIX manual pages of the software package. Has the same substructure as ```/usr/share/man```. |
| ```/opt/<provider>``` | Optional | ```<provider>``` is [LANANA](http://www.lanana.org/) registered provider name. Recommended that packages are installed in ```/opt/<provider>/<package>``` and follow a similar structure of ```/opt/<package>```. |
| ```/opt/bin``` | Reserved | Reserved for local system administrator use. |
| ```/opt/doc``` | Reserved | Reserved for local system administrator use. |
| ```/opt/include``` | Reserved | Reserved for local system administrator use. |
| ```/opt/info``` | Reserved | Reserved for local system administrator use. |
| ```/opt/lib``` | Reserved | Reserved for local system administrator use. |
| ```/opt/man``` | Reserved | Reserved for local system administrator use. |
| **```/proc```** | ***De-facto*** | Kernel and process information virtual filesystem. |
| **```/root```** | Optional | Home directory for the root user. |
| **```/run```** | **Required** | Data relevant to running processes since system was booted. The purposes of this directory were once served by ```/var/run```. |
| ```/run/<program-name>.pid``` | Optional | Process identifier (PID) files, which were originally placed in ```/etc```, must be placed in ```/run```. The file contains the process identifier in ASCII-encoded decimal, followed by a newline character. |
| **```/sbin```** | **Required** | Essential system binaries used for system administration (and other root-only commands) are stored in ```/sbin```, ```/usr/sbin```, and ```/usr/local/sbin```. ```/sbin``` contains binaries essential for booting, restoring, recovering, and/or repairing the system in addition to the binaries in ```/bin```. Must be no subdirectories in ```/sbin```. |
| **```/srv```** | **Required** | Site-specific data for services provided by this system. |
| **```/sys```** | ***Required*** | **Required for Linux**. Kernel and system information virtual filesystem. |
| **```/tmp```** | **Required** | Temporary files. Often not preserved between system reboots, see ```/var/tmp```. |
| **```/usr```** | **Required** | **Secondary hierarchy** for shareable, read-only user data. |
| ```/usr/bin``` | **Required** | Non-essential command binaries. This is the primary directory of executable commands on the system. Must be no subdirectories in ```/usr/bin```. |
| ```/usr/games``` | Optional | Games and educational binaries. |
| ```/usr/include``` | Optional | Header files included by C programs. |
| ```/usr/include/bsd``` | Optional | BSD compatibility include files. |
| ```/usr/lib``` | **Required** | Libraries for the binaries in ```/usr/bin/``` and ```/usr/sbin/```. Applications may use a single subdirectory under ```/usr/lib```. |
| ```/usr/lib/sendmail``` | Optional | Symbolic link to the *sendmail*-compatible command for historical reasons. |
| ```/usr/libexec``` | Optional | Binaries run by other programs. Applications may use a single subdirectory under ```/usr/libexec```. |
| ```/usr/lib<qual>``` | Optional | Alternate format libraries, which performs the same role as ```/usr/lib```. The symbolic links ```/usr/lib<qual>/sendmail``` and ```/usr/lib<qual>/X11``` are not required. |
| **```/usr/local```** | **Required** | **Tertiary hierarchy** for local data, specific to this host. |
| ```/usr/local/bin``` | **Required** | Local binaries. |
| ```/usr/local/etc``` | **Required** | Host-specific system configuration for local binaries. ```/usr/local/etc``` may be a symbolic link to ```/etc/local```. NOTE: ```/usr/etc``` is not allowed: programs in ```/usr``` should place configuration files in ```/etc```. |
| ```/usr/local/games``` | **Required** | Local game binaries. |
| ```/usr/local/include``` | **Required** | Local C header files. |
| ```/usr/local/lib``` | **Required** | Local libraries. |
| ```/usr/local/lib<qual>``` | Optional | Exist only if ```/lib<qual>``` or ```/usr/lib<qual>``` exist. |
| ```/usr/local/man``` | **Required** | Local online manuals. |
| ```/usr/local/sbin``` | **Required** | Local system binaries. |
| ```/usr/local/share``` | **Required** | Local architecture-independent hierarchy. The requirements for the contents of this directory are the same as for ```/usr/share```. |
| ```/usr/local/share/color``` | Optional | Exist only if ```/usr/share/color``` exists. It follows the same rules as ```/usr/share/color```. |
| ```/usr/local/src``` | **Required** | Local source code. |
| ```/usr/sbin``` | **Required** | Non-essential standard system binaries. Must be no subdirectories in ```/usr/sbin```. |
| ```/usr/share``` | **Required** | Shareable, read-only, architecture-independent data. Recommended that a subdirectory be used in ```/usr/share``` for any program or package. Applications using a single file may use ```/usr/share/misc```. |
| ```/usr/share/color``` | Optional | Color management information. The top-level directory ```/usr/share/color``` must not contain any files; all files should be in subdirectories of ```/usr/share/color```. |
| ```/usr/share/color/icc``` | Optional | ICC color profiles. |
| ```/usr/share/dict``` | Optional | Word lists. |
| ```/usr/share/dict/words``` | Optional | List of English words. |
| ```/usr/share/doc``` | Optional | Miscellaneous documentation. |
| ```/usr/share/games``` | Optional | Static data files for ```/usr/games```. Any modifiable files, such as score files, game play logs, and so forth, should be placed in ```/var/games```. |
| ```/usr/share/info``` | Optional | Primary directory for GNU Info system. |
| ```/usr/share/locale``` | Optional | Locale information. |
| ```/usr/share/man``` | **Required** | Manual pages for commands and data under the ```/``` and ```/usr``` filesystems. This is the primary ```<mandir>``` of the system. Manual pages are stored in ```<mandir>/<locale>/man<section>```. |
| ```/usr/share/man/man1``` | Optional | User programs. |
| ```/usr/share/man/man2``` | Optional | System calls. |
| ```/usr/share/man/man3``` | Optional | Library calls. |
| ```/usr/share/man/man4``` | Optional | Special files. |
| ```/usr/share/man/man5``` | Optional | File formats. |
| ```/usr/share/man/man6``` | Optional | Games. |
| ```/usr/share/man/man7``` | Optional | Miscellaneous. |
| ```/usr/share/man/man8``` | Optional | System administration. |
| ```/usr/share/man/<locale>/man<section>``` | Optional | Manual pages for specific ```<locale>``` and ```<section>```. The ```<locale>``` is based on Appendix E of the POSIX 1003.1 standard and has format ```<lang>[_<terr>][.<char-set>][,<ver>]```. |
| ```/usr/share/misc``` | **Required** | Miscellaneous architecture-independent data. |
| ```/usr/share/misc/ascii``` | Optional | ASCII character set table. |
| ```/usr/share/misc/termcap``` | Optional | Terminal capability database. |
| ```/usr/share/misc/termcap.db``` | Optional | Terminal capability database. |
| ```/usr/share/nls``` | Optional | Message catalogs for Native language support. |
| ```/usr/share/ppd``` | Optional | Printer definitions, that's PostScript Printer Definition (PPD) files. |
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
| ```/usr/src``` | Optional | Source code only for reference purposes. e.g., kernel source code with its header files. Generally, source should not be built within this hierarchy. |
| ```/usr/src/linux``` | Optional | It contains Linux kernel source code, or may be a symbolic link to a kernel source code tree. |
| ```/usr/X11R6``` | Optional | X Window System, Version 11, Release 6 (up to FHS-2.3). |
| ```/usr/spool``` | Optional | Symbolic links to ```/var/spool``` for backwards compatibility. |
| ```/usr/spool/locks``` | Optional | Symbolic links to ```/var/lock``` for backwards compatibility. |
| ```/usr/tmp``` | Optional | Symbolic links to ```/var/tmp``` for backwards compatibility. |
| **```/var```** | **Required** | Variable files. ```/var``` is specified in order to make it possible to mount ```/usr``` read-only. Some portions of ```/var``` are not shareable between different systems, such as ```/var/log```, ```/var/lock``` and ```/var/run```. Other portions may be shared, such as ```/var/mail``` and ```/var/cache/man```. |
| ```/var/account``` | Optional | Current active process accounting logs. |
| ```/var/backups``` | Reserved | Reserved to prevent conflict with historical and/or local practice. |
| ```/var/cache``` | **Required** | Application cache data. The data must remain valid between invocations of the application and rebooting the system, and may be expired in an application specific manner, by the system administrator, or both. |
| ```/var/cache/fonts``` | Optional | Locally-generated fonts. |
| ```/var/cache/man``` | Optional | Locally-formatted manual pages. |
| ```/var/cache/www``` | Optional | WWW proxy or cache data. |
| ```/var/cache/<package>``` | Optional | Package specific cache data. |
| ```/var/crash``` | Optional | System crash dumps. |
| ```/var/cron``` | Reserved | Reserved to prevent conflict with historical and/or local practice. |
| ```/var/games``` | Optional | Variable game data relating to games in ```/usr```. |
| ```/var/lib``` | **Required** | Variable state information pertaining to an application or the system. State information should generally remain valid after a reboot, should not be logging output, and should not be spooled data. An application must use a subdirectory of ```/var/lib``` for its data. |
| ```/var/lib/<editor>``` | Optional | Editor backup files and state. |
| ```/var/lib/<pkgtool>``` | Optional | Packaging support files. |
| ```/var/lib/<package>``` | Optional | State data for packages and subsystems. |
| ```/var/lib/color``` | Optional | Color management information. This directory shall be laid out using the same rules as the ```/usr/share/color``` directory. |
| ```/var/lib/hwclock``` | Optional | State directory for hwclock. |
| ```/var/lib/misc``` | **Required** | Miscellaneous variable data, which is intended for state files that don't need a subdirectory. |
| ```/var/lib/xdm``` | Optional | X display manager variable data. |
| ```/var/local``` | **Required** | Variable data for ```/usr/local```. |
| ```/var/lock``` | **Required** | Lock files keeping track of resources currently in use. The naming convention which must be used is "LCK.." followed by the base name of the device. |
| ```/var/log``` | **Required** | Log files and directories. |
| ```/var/log/lastlog``` | Optional | Record of last login of each user. |
| ```/var/log/messages``` | Optional | System messages from syslogd. |
| ```/var/log/wtmp``` | Optional | Record of all logins and logouts. |
| ```/var/mail``` | Optional | User mailbox files, which must be stored in the standard UNIX mailbox format. Note that ```/var/mail``` may be a symbolic link to another directory. |
| ```/var/msgs``` | Reserved | Reserved to prevent conflict with historical and/or local practice. |
| ```/var/opt``` | **Required** | Variable data from add-on software packages that are stored in ```/opt/```. |
| ```/var/opt/<subdir>``` | Optional | Variable data of the add-on software package in ```/opt/<subdir>``` must be installed in ```/var/opt/<subdir>```. |
| ```/var/preserve``` | Reserved | Reserved to prevent conflict with historical and/or local practice. |
| ```/var/run``` | **Required** | Data relevant to running processes. The ```/var/run``` is used for the purposes of backwards compatibility. Migration to use ```/run``` is recommended. It's valid to implement ```/var/run``` as a symlink to ```/run```. |
| ```/var/spool``` | **Required** | Application spool data, which is awaiting some kind of later processing. |
| ```/var/spool/cron``` | ***Required*** | **Required for Linux**. Contain the variable data for the **cron** and **at** programs. |
| ```/var/spool/lpd``` | Optional | Printer spool directory. |
| ```/var/spool/lpd/printer``` | Optional | Spools for a specific printer. |
| ```/var/spool/mqueue``` | Optional | Outgoing mail queue. |
| ```/var/spool/news``` | Optional | News spool directory. |
| ```/var/spool/rwho``` | Optional | Rwhod files, which hold the rwhod information for other systems on the local net. |
| ```/var/spool/uucp``` | Optional | Spool directory for UUCP. |
| ```/var/tmp``` | **Required** | Temporary files to be preserved between reboots.|
| ```/var/yp``` | Optional | Network Information Service (NIS) database files. Formerly known as the Sun Yellow Pages (YP). |

# Linux Standard Base (LSB)

The [Linux Standard Base (LSB)](http://refspecs.linuxfoundation.org/lsb.shtml) was created to lower the overall costs of supporting the Linux platform. By reducing the differences between individual Linux distributions, the LSB greatly reduces the costs involved with porting applications to different distributions, as well as lowers the cost and effort involved in after-market support of those applications.

The picture below represents the key LSB deliverables for application and distribution developers:
![LSB Specifications and Tools](/assets/lsb_concept_tools.png)

## LSB Specifications

The official home of the LSB specification is the [Linux Foundation's Reference Specifications Archive](http://refspecs.linuxfoundation.org/lsb.shtml). The following LSB specifications are released:

* **LSB 1.0** was released on June 29, 2001.

    LSB 1.0 supports [Filesystem Hierarchy Standard (FHS) 2.2](http://refspecs.linuxfoundation.org/LSB_1.0.0/gLSB/fhs.html).

* **LSB 1.1** was released on January 22, 2002.

    LSB 1.1 supports [Filesystem Hierarchy Standard (FHS) 2.2](http://refspecs.linuxfoundation.org/LSB_1.1.0/gLSB/execenvfhs.html).

* **LSB 1.2** was released on June 28, 2002.

    LSB 1.2 supports [Filesystem Hierarchy Standard (FHS) 2.2](http://refspecs.linuxfoundation.org/LSB_1.2.0/gLSB/execenvfhs.html).

* **LSB 1.3** was released on December 17, 2002.

    LSB 1.3 supports [Filesystem Hierarchy Standard (FHS) 2.2](http://refspecs.linuxfoundation.org/LSB_1.3.0/gLSB/gLSB/execenvfhs.html).

* **LSB 2.0** was released on August 31, 2004. The release omitted the PPC32 and S390 architectures.

    LSB 2.0 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_2.0.0/LSB-Core/LSB-Core/normativerefs.html#STD.FHS).

* **LSB 2.0.1** was released on October 21, 2004.

    LSB 2.0.1 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_2.0.1/LSB-Core/LSB-Core/normativerefs.html#STD.FHS).

* **LSB 2.1** was released on March 11, 2005.

    LSB 3.0 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_2.1.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

* **LSB 3.0** was released on July 6, 2005.

    LSB 3.0 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_3.0.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

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

    There is also [ISO/IEC TR 24715:2006](http://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=38825) which identifies areas of conflict between **ISO/IEC 23360** (the Linux Standard Base 3.1 specification) and the **ISO/IEC 9945:2003** (POSIX) International Standard. The **ISO/IEC TR 24715:2006** can be downloaded from [Publicly Available Standards](http://standards.iso.org/ittf/PubliclyAvailableStandards/index.html).

    LSB 3.1 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_3.1.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

* **LSB 3.2** was released on January 25, 2008

    Note that the LSB 3.2 Core specification is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

    LSB 3.2 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_3.2.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

* **LSB 4.0** was released on May 1, 2009

    Note that the LSB 4.0 Core specification is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

    LSB 4.0 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_4.0.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

* **LSB 4.1** was released on February 16, 2011

    Note that the LSB 4.1 Core specification is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard.

    LSB 4.1 supports [Filesystem Hierarchy Standard (FHS) 2.3](http://refspecs.linuxfoundation.org/LSB_4.1.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

* **LSB 5.0** was released on June 3, 2015.

    Note that the LSB 5.0 Core specification set is an evolution of the ISO/IEC International Standard 23360, which corresponded to LSB 3.1. This edition is not to be considered an ISO standard. LSB 5.0 contains two major changes to the specification: (1) the first major release to **break 100% compatibility with earlier versions**. It is compatible with LSB 3.0, and mostly compatible with LSB 3.1 and later, with one exception (Qt 3 Removed); (2) LSB 5.0 supports seven architectures: IA32, IA64, PPC32, PPC64, S390, S390X, and X86_64.

    LSB 5.0 supports [Filesystem Hierarchy Standard (FHS) 3.0](http://refspecs.linuxfoundation.org/LSB_5.0.0/LSB-Core-generic/LSB-Core-generic/normativerefs.html#STD.FHS).

The Linux Standard Base (LSB) specifications are made available in two parts: **an architecture independent (generic) part** and **an architecture dependent part**. For LSB 5.0, the architecture independent part is comprised of five modules: **Common**, **Core**, **Desktop**, **Runtime Languages** and **Imaging**. The architecture dependent part is comprised of two modules: **Core** and **Desktop**.

Also, there are **mandatory** and **trial use** modules in the specification. The former impose mandatory requirements on LSB compliant distributions and applications may safely rely on the functionality described in mandatory modules. Functionality in trial use modules is not required in LSB compliant distributions and applications should take this into consideration. Meanwhile, trial use modules represent candidates for inclusion in the next versions of LSB.

## LSB Navigator

**LSB Database** is a central place for storing information about the LSB standard and about the surrounding Linux ecosystem. [LSB Navigator](http://www.linuxbase.org/navigator/commons/welcome.php) represents web based interface over all these information. It can be used by Linux developers, Linux distribution vendors and LSB workgroup to browse, query, analyze and submit various information.

### LSB Elements

There are four [Top Level Entities](http://www.linuxbase.org/navigator/browse/index.php) of LSB specifiction: **Modules**, **ELF Elements**, **RPM Tags** and **Interpreted Languages**. And the [Modules](http://www.linuxbase.org/navigator/browse/module.php) contains [ABI (Libraries)](http://www.linuxbase.org/navigator/browse/abi.php) and [Commands](http://www.linuxbase.org/navigator/browse/command.php). The [ELF Elements](http://www.linuxbase.org/navigator/browse/elfindex.php) and [RPM Tags](http://www.linuxbase.org/navigator/browse/rpmtag.php) belong to [LSB_Core](http://www.linuxbase.org/navigator/browse/module.php?cmd=display_module&module=LSB_Core) module only. The [Interpreted Languages](http://www.linuxbase.org/navigator/browse/intlang.php) contains **Java**, **Perl** and **Python** languages.

![Top Level Schema of LSB Elements](/assets/top_level_of_lsb_elements.png)

## LSB Certification

This part of the [LSB Certification System](https://www.linuxbase.org/lsb-cert/welcome_cert.php) represents central place for managing certification workflow and status. In that website, you can track the industry picture of LSB certification in **Product Directory** area. For instance, a list of Linux distributions and applications certified for compliance with the LSB standard can be found [here](https://www.linuxbase.org/lsb-cert/productdir.php?by_prod).

## Additional Requirements for FHS in LSB 3.1

An **LSB conforming application** shall conform to the [Filesystem Hierarchy Standard (FHS)](http://refspecs.linuxfoundation.org/lsb.shtml).

An **LSB conforming implementation** shall provide the mandatory portions of the file system hierarchy specified in the [Filesystem Hierarchy Standard (FHS)](http://refspecs.linuxfoundation.org/lsb.shtml), together with following additional requirements made in [LSB specification 3.1](http://refspecs.linuxfoundation.org/LSB_3.1.0/LSB-Core-generic/LSB-Core-generic/execenvfhs.html).

| Directory | Requirement | Description |
| :-------- | :---------: | :---------- |
| **```/dev```** | **Required** | Device files. |
| ```/dev/null``` | **Required** | An infinite data source and data sink. Data written to this device shall be discarded. Reads from this device shall always return end-of-file (EOF). |
| ```/dev/zero``` | **Required** | An infinite data source and data sink. |
| ```/dev/null``` | **Required** | This device is a source of zeroed out data. All data written to this device shall be discarded. A read from this device shall always return the requested number of bytes, each initialized to the value ```\0```. |
| ```/dev/tty``` | **Required** | In each process, a synonym for the controlling terminal associated with the process group of that process, if any. All reads and writes to this device shall behave as if the actual controlling terminal device had been opened. |
| **```/etc```** | **Required** | Host-specific system configuration. Recommended that configuration files are stored in subdirectories of ```/etc``` rather than directly in ```/etc```. |
| ```/etc/cron.d``` | **Required** | A directory containing extended crontab files, refer to [Cron Jobs](http://refspecs.linuxfoundation.org/LSB_3.1.0/LSB-Core-generic/LSB-Core-generic/sysinit.html#CRONJOBS). |
| ```/etc/cron.daily``` | **Required** | A directory containing shell scripts to be executed once a day. |
| ```/etc/cron.hourly``` | **Required** | A directory containing shell scripts to be executed once per hour. |
| ```/etc/cron.monthly``` | **Required** | A directory containing shell scripts to be executed once per month. |
| ```/etc/cron.weekly``` | **Required** | A directory containing shell scripts to be executed once a week. |
| ```/etc/init.d``` | **Required** | A directory containing system initialization scripts. |
| ```/etc/profile.d``` | **Required** | A directory containing shell scripts. Script names should follow the same conventions as specified for cron jobs, but should have the suffix ```.sh```. The behavior is unspecified if a script is installed in this directory that does not have the suffix ```.sh```. |

# References

[Filesystem Hierarchy Standard (FHS) on Linux Foundation](http://www.linuxfoundation.org/collaborate/workgroups/lsb/fhs)
[Filesystem Hierarchy Standard (FHS) Specifications Archive](http://refspecs.linuxfoundation.org/lsb.shtml)
[Linux Standard Base (LSB) Specifications Archive](http://refspecs.linuxfoundation.org/lsb.shtml)
[Linux Standard Base (LSB) Navigator](http://standards.iso.org/ittf/PubliclyAvailableStandards/index.html)
[Linux Standard Base (LSB) Certification System](https://www.linuxbase.org/lsb-cert/welcome_cert.php)
[Publicly Available Standards](http://standards.iso.org/ittf/PubliclyAvailableStandards/index.html)