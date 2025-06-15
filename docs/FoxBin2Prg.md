# FoxBin2Prg Home
Documentation of FoxBin2Prg - A Binary to Text converter for MS Visual Foxpro 9

## Purpose of this document
This document introduce the basic ideas of FoxBin2Prg

The original document was created by [Fernando D. Bozzo](https://github.com/fdbozzo) whom I like to thank for the great project.   
Pictures are taken from the original project.  
As far as possible these are the original documents. Changes are added where functionality is changed.

----
## Table of contents
- [Use](#use)
- [Download for development](#download-for-development)
- [Requirements](#requirements)
- [What is FoxBin2Prg](#what-is-foxbin2prg)
- [Advantages](#advantages)
- [Example](#example)
- [Limitations](#limitations)
- [Usage](#usage)
- [Keep reading](#keep-reading)

## Use
- Download the [runtime](https://github.com/fdbozzo/foxbin2prg/blob/master/ThorUpdater/FoxBin2Prg.zip) (same as used by Thor)
- Or (best) install via [Thor](https://github.com/VFPX/Thor/blob/master/Docs/Thor_install.md), this keeps you on the latest version.

## Download for development
### Source
Original repository at https://github.com/fdbozzo/foxbin2prg.   
### Rebuild additional files
Regenerate after download / clone / pull from https://github.com/fdbozzo/foxbin2prg.   
**Note: You you must run FoxBin2Prg against itself to create the binaries and exes.**   
Run:
```
CD "path_to_FoxBin2Prg"
*This uses a special configuration
DO ReCreate_FoxBin2Prg.prg
```   
**Note: Do not run FoxBin2Prg.prg directly.**   
**Note:** It is intended that there will be an error about _TESTS\FXUResults.db2_. This file could not be recreated because its per-dbf-configuration in _TESTS\FXUResults.dbf.cfg_ is set this way.
The message says, FoxBin2Prg is doing this well. The message might no be at optimum, but this is the way the system runs. Feel free to add a besser message.

## Requirements
- A copy of MS VFP9 SP1, at least _3504_
- Runs with VFPA (Note, you need to recompile the EXE or use the PRG)

## Demo video
[See YouTube demo video of FoxBin2Prg used with PlasticSCM](http://youtu.be/sE4wQ50Itqg)

## What is FoxBin2Prg
It is a program intended to be used with **SCM** tools (Source Code Managers, like VSS, CVS, SVN)
and **DVCS** tools (like git, Mercurial, Plastic, and others),
or as **standalone** program for _Diff_ (viewing differences) and _Merge_ operations,
that pretends to substitute _SccText/X_ and _TwoFox_ and enhance their functionality,
generating bidirectional PRG-Style versions that allow recreating the original binary file.  

## Advantages
- It generates _Text_ style programs (not compilable), for visual comparison out of FoxPros table based code.
- It enables the change of the _Text_ version as easy as modifying a PRG
- All the program code is in just one PRG, to simplify its maintainability
- Out of the _Text_ versions you can **generate the original binaries**, so it is useful as backup
- The extensions are configurable if you create a FOXBIN2PRG.CFG file
  - Inheritance of CFG configuration files between directories
- Special configuration per table, allowing additional non structural index files, sorting and ranges of records to include
- Methods and properties of _Text_ version are alphabetically sorted for easy comparison
- Can set _UseClassPerFile_ setting to create individual files by class
- Can set _UseFilesPerDBC_ setting to create individual files by DBC member
- Takes advantage of the API using foxbin2prg as an object
- It has compatibility with SccText/X at parameter level so can be used as substitute with SourceSafe
- Productivity: You can create a shortcut in the "SendTo" folder on your user Windows Profile, so you can "send" the selected file (pjx, pj2, etc) to Foxbin2prg.exe and make on-the-fly conversions
- Modify the _Text_ Prg-Style versions with MODIFY COMMAND (without compile) to see colored syntax, or even use the Document View to navigate the procedures
- Get back your SourceSafe projects (.pjx) from their .pjm files 
- Don't infest a text based system like git with binaries

Currently supports the conversion between PJX, SCX, VCX, FRX, LBX, DBC, DBF, MNX, MEM and FKY files,
for which a _Text_ version is generated with pj2, sc2, vc2, fr2, lb2, dc2, db2, mn2, me2 and fk2 extensions.
The extensions may be reconfigured to be compatible with SCCAPI (just tested with SourceSafe).

## Example
![FoxBin2prg_scctextx-vs-FoxBin2Prg_scx_EN.png](pictures/FoxBin2prg_scctextx-vs-FoxBin2Prg_scx_EN.png)   
![FoxBin2prg_scctextx-vs-FoxBin2Prg_mnx_EN.png](pictures/FoxBin2prg_scctextx-vs-FoxBin2Prg_mnx_EN.png)   

## Limitations
If dealing with project files, FoxBin2Prg will fail if files of the project are not stored on the drive of the project.
See [issue #93](https://github.com/fdbozzo/foxbin2prg/issues/93).

## Usage
FoxBin2Prg can be used in tree ways:
1. [EXE version](./FoxBin2Prg_Run.md): (Recommended and fastest)   
   - All-inclusive, you just need foxbin2prg.exe and filename_caps.exe/cfg.   
   - Runs from windows
   - If run from IDE, the EXE needs to be compiled for the version of FoxPro.
1. [PRG version](./FoxBin2Prg_Run.md):   
   - You need various files: foxbin2prg.prg, all the props*.txt files and filename_caps.exe/cfg.
   - Runs out of VFP IDE, no problems mixing VFP 9 and VFPA
1. [Object version](./FoxBin2Prg_Object.md):
   - Usable out of own code
   - expandable

## Keep reading
- [FoxBin2Prg Full Change History](./ChangeLog.md)
- [FoxBin2Prg Internals and Configuration](./FoxBin2Prg_Internals.md)
- [FoxBin2Prg and use with SCM tools](./FoxBin2Prg_SCM.md)
- [FoxBin2Prg and use with git](./FoxBin2Prg_git.md)

----
![VFPX logo](https://vfpx.github.io/images/vfpxbanner_small.gif)   
This project is part of [VFPX](https://vfpx.github.io/).

----
Last changed: _2023/12/05_ ![Picture](./pictures/vfpxpoweredby_alternative.gif)