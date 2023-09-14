# About

Xash3D FWGS engine fork. I've forked this engine to obtain a "frozen" copy that can be compiled in Repka Pi without any issues.

Instruction below copied from original repository with some changes (removed all about windows and x86 platform, also edited link for "git clone" command).

## Build instructions

NOTE: NEVER USE GitHub's ZIP ARCHIVES. GitHub doesn't include external dependencies!

### Prerequisites

On Repka Pi you also need to compile [Half-Life SDK](https://github.com/FWGS/hlsdk-portable).
This repository contains fork of HLSDK from FWGS and restored source code for some of the mods. Not all of them, of course.

##### Debian/Ubuntu

`$ sudo apt install build-essential python libsdl2-dev libfontconfig-dev libfreetype6-dev`
* Clone this repostory:
`$ git clone --recursive https://github.com/ArtSvetlakov/xash3d-fwgs-repkapi.git`

### Building

0) Examine which build options are available: `./waf --help`
1) Configure build: `./waf configure -T release --jobs=4 --disable-gl --enable-gles1 --disable-menu-changegame`
2) Compile: `./waf build`
3) Install to some folder (for example): `./waf install --destdir=~/games/xash3d`
