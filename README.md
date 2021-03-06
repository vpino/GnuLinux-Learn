# Version in English

## Before to start with canaima, you need learn about Unix, Linux Kernel and GNU

## Unix:

![Unix logo](http://upload.wikimedia.org/wikipedia/commons/2/2e/UNIX%C2%AE.png "Unix")

Is a family of multitasking, multiuser computer operating systems that derive from the original AT&T Unix, developed in the 1970s at the Bell Labs research center by Ken Thompson, Dennis Ritchie, and others.


## Linux:

![Linux logo](https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Tux.svg/150px-Tux.svg.png "Linux")

Linux is a clone of the operating system Unix, written from scratch by
Linus Torvalds with assistance from a loosely-knit team of hackers across the Net. It aims towards POSIX and Single UNIX Specification compliance.

It has all the features you would expect in a modern fully-fledged Unix, including true multitasking, virtual memory, shared libraries, demand loading, shared copy-on-write executables, proper memory management, and multistack networking including IPv4 and IPv6.


## Kernel

![kernel logo](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Kernel-microkernel.svg/250px-Kernel-microkernel.svg.png "kernel")

The kernel or linux kernel can be defined as the heart of this operating system. It is the one in charge that the software and the hardware of your computer can work together.

The most important functions of the same, although not the only, are:

* Memory management for all running programs and processes.

* Managing the processor time that running programs and processes use.
    
* It is the one in charge of that we can access the peripherals / elements of our computer in a comfortable way.


## GNU

![GNU logo](https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Heckert_GNU_white.svg/245px-Heckert_GNU_white.svg.png "GNU") 


GNU is an operating system and an extensive collection of computer software. GNU is composed wholly of free software, most of which is licensed under GNU's own GPL.


## GNU/Linux

![GNU/Linux logo](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Gnulinux.svg/170px-Gnulinux.svg.png "GNU/Linux") 


GNU / Linux is one of the terms used to refer to the combination of the free kernel or kernel similar to Unix called Linux with the GNU operating system. Its development is one of the most prominent examples of free software; All of its source code may be freely used, modified and redistributed by anyone under the terms of the GNU General Public License (GPL) and another set of free licenses.

Although "Linux" is referred to in everyday jargon as the operating system, this is actually only the kernel of the system. The real name of the operating system is "GNU / Linux" because the rest of the system (the fundamental part of the interaction between the hardware and the user) is handled with GNU project tools (www.gnu.org) and Desktop environments (such as GNOME), which is also part of the GNU project although it had an independent origin.


## Linux Distribution

![Distribution Linux logo](https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/Arquitectura_linux.png/250px-Arquitectura_linux.png "Distribution Linux") 


A Linux distribution (often abbreviated as distro) is an operating system made from a software collection, which is based upon the Linux kernel and, often, a package management system. Linux users usually obtain their operating system by downloading one of the Linux distributions, which are available for a wide variety of systems ranging from embedded devices (for example, OpenWrt) and personal computers (for example, Linux Mint) to powerful supercomputers (for example, Rocks Cluster Distribution).

A typical Linux distribution comprises a Linux kernel, GNU tools and libraries, additional software, documentation, a window system (the most common being the X Window System), a window manager, and a desktop environment. Most of the included software is free and open-source software made available both as compiled binaries and in source code form, allowing modifications to the original software. Usually, Linux distributions optionally include some proprietary software that may not be available in source code form, such as binary blobs required for some device drivers.

## Meta Distribution

It is called Meta distribution to build other software from an existing version of GNU / Linux. GNU / Linux Distributions:


## Filesystem Hierarchy Standard 

This standard consists of a set of requirements and guidelines for file and directory placement under UNIX-like
operating systems. The guidelines are intended to support interoperability of applications, system administration
tools, development tools, and scripts as well as greater uniformity of documentation for these systems.


### The Filesystem

This standard assumes that the operating system underlying an FHS-compliant file system supports the same
basic security features found in most UNIX filesystems.
It is possible to define two independent distinctions among files: shareable vs. unshareable and variable vs. static.

In general, files that differ in either of these respects should be located in different directories. This makes it easy
to store files with different usage characteristics on different filesystems.

"Shareable" files are those that can be stored on one host and used on others. "Unshareable" files are those that
are not shareable. For example, the files in user home directories are shareable whereas device lock files are not.
"Static" files include binaries, libraries, documentation files and other files that do not change without system
administrator intervention. "Variable" files are files that are not static.

Here is an example of a FHS-compliant system. (Other FHS-compliant layouts are possible.)

|               | shareable       | unshareable  |
| ------------- |:---------------:| ------------:|
| static        | /usr  , /opt  |   /etc, /boot   |
| variable      | /var/mail, /var/spool/news | /var/run, /var/lock    |


## The Root Filesystem

### Purpose

The contents of the root filesystem must be adequate to boot, restore, recover, and/or repair the system.

* To boot a system, enough must be present on the root partition to mount other filesystems. This includes utilities, configuration, boot loader information, and other essential start-up data. /usr, /opt and /var are designed such that they may be located on other partitions or filesystems.

* To enable recovery and/or repair of a system, those utilities needed by an experienced maintainer to diagnose and reconstruct a damaged system must be present on the root filesystem.

* To restore a system, those utilities needed to restore from system backups (on floppy, tape, etc.) must be present on the root filesystem

#### Rationale

* Creating a new subdirectory of the root filesystem is prohibited.

* Applications must never create or require special files or subdirectories in the root directory. Other locations in the OHS hierarchy provide more than enough flexibility for any package.

### Requirements

The following directories, or symbolic links to directories, are required in /

| **Directory**         | **Description**                               |
| :-----------------|:---------------------------------------------:|
| **bin**               | Essential command binaries                    |
| **boot**              | Static files of the boot loader               |
| **dev**               | Device files                                  |
| **etc**               | Host-specific system configuration            |
| **lib**               | Essential shared libraries and kernel modules |
| **media**             | Mount point for removeable media              |
| **mnt**               | Mount point for mounting a filesystem temporarily |
| **opt**               | Add-on application software packages          |
| **sbin**              | Essential system binaries                     |
| **srv**               | Data for services provided by this system     |
| **tmp**               | Temporary files                               |
| **usr**               | Secondary hierarchy                           |
| **var**               | Variable data                                 |

Each directory listed above is specified in detail in separate subsections below. /usr and /var each have a complete section in this document due to the complexity of those directories

### Specific Options

The following directories, or symbolic links to directories, must be in /, if the corresponding subsystem is installed.

| **Directory**         | **Description**                         |
| :-----------------|:-----------------------------------:|
| home              | User home directories (optional)    |
| lib<qual>         | Alternate format essential shared libraries (optional) |
| root              | Home directory for the root user (optional) |

Each directory listed above is specified in detail in separate subsections below

### /bin: 

#### Purpose

/bin contains commands that may be used by both the system administrator and by users, but which are required when no other filesystems are mounted (e.g. in single user mode). It may also contain commands which are used indirectly by scripts. 


#### Requirements

There must be no subdirectories in /bin.
The following commands, or symbolic links to commands, are required in /bin 

| **Directory**         | **Description**                               |
| :---------------------|:---------------------------------------------:|
| **cat** 				| Utility to concatenate files to standard output |
| **chgrp** 			| Utility to change file group ownership		|
| **chmod**				| Utility to change file access permissions		|
| **chown** 			| Utility to change file owner and group		|
| **cp** 				| Utility to copy files and directories			|
| **date** 				| Utility to print or set the system data and time |
| **dd** 				| Utility to convert and copy a file 			|
| **df** 				| Utility to report filesystem disk space usage |
| **dmesg** 			| Utility to print or control the kernel message buffer |
| **echo** 				| Utility to display a line of text 			|
| **false** 			| Utility to do nothing, unsuccessfully 		|
| **hostname** 			| Utility to show or set the system’s host name |
| **kill** 				| Utility to send signals to processes 			|
| **ln** 				| Utility to make links between files 			|
| **login**  			| Utility to begin a session on the system  	|
| **ls**  				| Utility to list directory contents 			|
| **mkdir** 			| Utility to make directories 					|
| **mknod** 			| Utility to make block or character special files |
| **more** 				| Utility to page through text 					|
| **mount** 			| Utility to mount a filesystem 				|
| **mv** 				| Utility to move/rename files 					|
| **ps** 				| Utility to report process status 				|
| **pwd** 				| Utility to print name of current working directory |
| **rm** 				| Utility to remove files or directories 		|
| **rmdir**  			| Utility to remove empty directories 			|
| **sed** 				| The ‘sed’ stream editor 						|
| **sh** 				| The Bourne command shell 						|
| **stty** 				| Utility to change and print terminal line settings |
| **su**  				| Utility to change user ID 					|
| **sync** 				| Utility to flush filesystem buffers 			|
| **true** 				| Utility to do nothing, successfully 			|
| **umount** 			| Utility to unmount file systems 				|
| **uname** 			| Utility to print system information 			|

If /bin/sh is not a true Bourne shell, it must be a hard or symbolic link to the real shell command.
The [ and test commands must be placed together in either /bin or /usr/bin.


#### Specific Options

The following programs, or symbolic links to programs, must be in /bin if the corresponding subsystem is installed:

| **Directory**         | **Description**                               |
| :---------------------|:---------------------------------------------:|
| **csh** 				| The C shell (optional) 						|
| **ed** 				| The ‘ed’ editor (optional) 					|
| **tar** 				| The tar archiving utility (optional) 			|
| **cpio** 				| The cpio archiving utility (optional) 		|
| **gzip** 				| The GNU compression utility (optional) 		|
| **gunzip** 			| The GNU uncompression utility (optional) 		|
| **zcat** 				| The GNU uncompression utility (optional)   	|
| **netstat** 			| The network statistics utility (optional) 	|
| **ping** 				| The ICMP network test utility (optional) 		|


## /boot : Static files of the boot loader

### Purpose

This directory contains everything required for the boot process except configuration files not needed at boot time and the map installer. Thus /boot stores data that is used before the kernel begins executing user-mode programs. This may include saved master boot sectors and sector map files.

### Specific Options

The operating system kernel must be located in either / or /boot

# Version en Español

![Venezuela logo](https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Flag_of_Venezuela.svg/200px-Flag_of_Venezuela.svg.png  "Venezuela")

## Antes de comenzar con canaima, necesitas saber sobre Unix, Linux y GNU:

## Unix:

![Unix logo](http://upload.wikimedia.org/wikipedia/commons/2/2e/UNIX%C2%AE.png "Unix")

Es un sistema operativo portable, multitarea y multiusuario; desarrollado, en principio, en 1970, por un grupo de empleados de los laboratorios Bell de AT&T, entre los que figuran Dennis Ritchie, Ken Thompson, Douglas McIlroy.

## Linux 

![Linux logo](https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Tux.svg/150px-Tux.svg.png "Linux")

Linux es un clon del sistema operativo Unix, escrito desde cero por Linus Torvalds con la ayuda de un equipo de hackers en la red. Apunta al cumplimiento de la especificación POSIX y Single UNIX.

 Tiene todas las características que usted esperaría en un Unix moderno y completo, incluyendo la verdadera multitarea, memoria virtual, bibliotecas compartidas, carga de la demanda, ejecutables compartidos de copia en escritura, administración de memoria adecuada y redes multiestack incluyendo IPv4 e IPv6.

## Kernel

![kernel logo](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Kernel-microkernel.svg/250px-Kernel-microkernel.svg.png "kernel")

El kernel ó núcleo de linux se puede definir como el corazón de este sistema operativo. Es el encargado de que el software y el hardware de tu ordenador puedan trabajar juntos.

Las funciones más importantes del mismo, aunque no las únicas, son:

* Administración de la memoria para todos los programas y procesos en ejecución.

* Administración del tiempo de procesador que los programas y procesos en ejecucion utilizan.
    
* Es el encargado de que podamos acceder a los periféricos/elementos de nuestro ordenador de una manera cómoda.


## GNU

![GNU logo](https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Heckert_GNU_white.svg/245px-Heckert_GNU_white.svg.png "GNU") 

GNU es un sistema operativo de tipo Unix desarrollado por y para el Proyecto GNU y auspiciado por la Free Software Foundation. Está formado en su totalidad por software libre, mayoritariamente bajo términos de copyleft. GNU es un acrónimo recursivo de "GNU's Not Unix" (en español: GNU no es Unix), elegido porque GNU sigue un diseño tipo Unix y se mantiene compatible con éste, pero se diferencia de Unix en que es software libre y que no contiene código de Unix

## GNU/Linux

![GNU/Linux logo](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Gnulinux.svg/170px-Gnulinux.svg.png "GNU/Linux")

GNU/Linux es uno de los términos empleados para referirse a la combinación del núcleo o kernel libre similar a Unix denominado Linux con el sistema operativo GNU. Su desarrollo es uno de los ejemplos más prominentes de software libre; todo su código fuente puede ser utilizado, modificado y redistribuido libremente por cualquiera bajo los términos de la GPL (Licencia Pública General de GNU,) y otra serie de licencias libres.

A pesar de que con "Linux" se denomina en la jerga cotidiana al sistema operativo, este es en realidad solo el Kernel (núcleo) del sistema. La verdadera denominación del sistema operativo es "GNU/Linux" debido a que el resto del sistema (la parte fundamental de la interacción entre el hardware y el usuario) se maneja con las herramientas del proyecto GNU (www.gnu.org) y con entornos de escritorio (como GNOME), que también forma parte del proyecto GNU aunque tuvo un origen independiente.

## Distribución Linux

![Distribution Linux logo](https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/Arquitectura_linux.png/250px-Arquitectura_linux.png "Distribution Linux") 

Una distribución Linux (coloquialmente llamada distro) es una distribución de software basada en el núcleo Linux que incluye determinados paquetes de software para satisfacer las necesidades de un grupo específico de usuarios, dando así origen a ediciones domésticas, empresariales y para servidores. Por lo general están compuestas, total o mayoritariamente, de software libre, aunque a menudo incorporan aplicaciones o controladores propietarios.

Además del núcleo Linux, las distribuciones incluyen habitualmente las bibliotecas y herramientas del proyecto GNU y el sistema de ventanas X Window System. Dependiendo del tipo de usuarios a los que la distribución esté dirigida se incluye también otro tipo de software como procesadores de texto, hoja de cálculo, reproductores multimedia, herramientas administrativas, etc. En el caso de incluir herramientas del proyecto GNU, se denomina distribución GNU/Linux.

## Meta Distribución

Se llama Meta distribución a construir otro software partiendo de una versión de GNU/Linux ya existente. Distribuciones GNU/Linux: 

