# About

Xash3D FWGS engine fork. I've forked this engine to obtain a "frozen" copy that can be compiled in Repka Pi without any issues.

Instruction below copied from original repository with some changes (removed all about windows and x86 platform, also edited link for "git clone" command).

## Install aarch64-release

1) install dependencies:
`$ sudo apt install libsdl2-dev libfontconfig-dev libfreetype6-dev`
2) extarct "xash3d-fwgs-repkapi_aarch64.zip" arcive
3) place the original half-life assets from its "valve" folder to xash3d/valve folder (except "dll" and "cl_dll", to get these folders you need to compile [Half-Life SDK](https://github.com/FWGS/hlsdk-portable))
4) Open terminal in "xash3d" folder and run: `$ ./xash3d`

## Build from source instructions

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
