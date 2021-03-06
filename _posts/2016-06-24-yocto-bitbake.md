---
layout: post
title: "Yocto Project & BitBake"
tag: RTOS
toc: true
---

This article introduces the **OpenEmbedded** project, **Yocto** project and **BitBake**.

<!--more-->

# OpenEmbedded

OpenEmbedded is a software framework used for creating Linux distributions aimed for, but not restricted to, [embedded devices](https://en.wikipedia.org/wiki/Embedded_system). The build system is based on BitBake recipes, which behave like [Gentoo Linux ebuilds](https://en.wikipedia.org/wiki/Ebuild).

# Yocto Project

The Yocto Project is an open source collaboration project that provides templates, tools and methods to help you create custom Linux-based systems for embedded products regardless of the hardware architecture. It was founded in 2010 as a collaboration among many hardware manufacturers, open-source operating systems vendors, and electronics companies to bring some order to the chaos of embedded Linux development.

Why use the Yocto Project? It's a complete embedded Linux development environment with tools, metadata, and documentation - everything you need. The free tools are easy to get started with, powerful to work with (including emulation environments, debuggers, an Application Toolkit Generator, etc.) and they allow projects to be carried forward over time without causing you to lose optimizations and investments made during the project’s prototype phase. The Yocto Project fosters community adoption of this open source technology allowing its users to focus on their specific product features and development.

The Yocto Project provides resources and information catering to both new and experienced users, and includes core system component recipes provided by the OpenEmbedded project. The Yocto Project also provides pointers to example code built demonstrating its capabilities. These community-tested images include the Yocto Project kernel and cover several build profiles across multiple architectures including ARM, PPC, MIPS, x86, and x86-64. Specific platform support takes the form of Board Support Package (BSP) layers for which a standard format has been developed. The project also provides an Eclipse IDE plug-in and a graphical user interface to the build system called Hob.

# BitBake

BitBake is a build engine that follows recipes in a specific format in order to perform sets of tasks. BitBake is a core component of the Yocto Project.

BitBake is a make-like build tool with the special focus of distributions and packages for embedded Linux cross compilation although it is not limited to that. It is inspired by Portage, which is the package management system used by the Gentoo Linux distribution. BitBake existed for some time in the OpenEmbedded project until it was separated out into a standalone, maintained, distribution-independent tool. BitBake is co-maintained by the Yocto Project and the OpenEmbedded project.

BitBake recipes specify how a particular package is built. It includes all the package dependencies, source code locations, configuration, compilation, build, install and remove instructions. It also stores the metadata for the package in standard variables.

The BitBake recipes consist of the source URL (http, https, ftp, cvs, svn, git, local file system) of the package, dependencies and compile or install options. During the build process they are used to track dependencies, performing native or cross-compilation of the package and package it so that it is suitable for installation on the local or a target device. It is also possible to create complete images consisting of a root file system and kernel. As a first step in a cross-build setup, the framework will attempt to create a cross-compiler toolchain suited for the target platform.

# References

* [OpenEmbedded Wikipedia](https://en.wikipedia.org/wiki/OpenEmbedded)
* [OpenEmbedded Official Site](http://www.openembedded.org/wiki/Main_Page)
* [OpenEmbedded User Manual](http://docs.openembedded.org/usermanual/usermanual.html)

* [Yocto Wikipedia](https://en.wikipedia.org/wiki/Yocto_Project)
* [Yocto Project](https://www.yoctoproject.org/)
* [Yocto Project Aligns Technology with OpenEmbedded and Gains Corporate Collaborators](http://www.linuxfoundation.org/news-media/announcements/2011/03/yocto-project-aligns-technology-openembedded-and-gains-corporate-co)
* [Deciding between Buildroot & Yocto](https://lwn.net/Articles/682540/)
* [Yocto Project Development Manual](http://www.yoctoproject.org/docs/current/dev-manual/dev-manual.html)
* [Yocto Project Quick Start](http://www.yoctoproject.org/docs/2.1/yocto-project-qs/yocto-project-qs.html)

* [BitBake Wikipedia](https://en.wikipedia.org/wiki/BitBake)
* [BitBake on Yocto Project](https://www.yoctoproject.org/tools-resources/projects/bitbake)
* [BitBake User Manual](http://www.yoctoproject.org/docs/current/bitbake-user-manual/bitbake-user-manual.html)
