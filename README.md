# About

Xash3D FWGS engine fork. I've forked this engine to obtain a "frozen" copy that can be compiled in Repka Pi without any issues.

Instruction below copied from original repository with some changes (removed all about windows and x86 platform, also edited link for "git clone" command).

## Build instructions
We are using Waf build system. If you have some Waf-related questions, I recommend you to read https://waf.io/book/

NOTE: NEVER USE GitHub's ZIP ARCHIVES. GitHub doesn't include external dependencies we're using!

### Prerequisites

If your CPU is x86 compatible, we are building 32-bit code by default. This was done to maintain compatibility with Steam releases of Half-Life and based on it's engine games.
Even if Xash3D FWGS does support targetting 64-bit, you can't load games without recompiling them from source code!

If your CPU is NOT x86 compatible or you decided build 64-bit version of engine, you may want to compile [Half-Life SDK](https://github.com/FWGS/hlsdk-portable).
This repository contains our fork of HLSDK and restored source code for some of the mods. Not all of them, of course.

#### GNU/Linux
##### Debian/Ubuntu

`$ sudo apt install build-essential python libsdl2-dev libfontconfig-dev libfreetype6-dev`
* Clone this repostory:
`$ git clone --recursive https://github.com/ArtSvetlakov/xash3d-fwgs-repkapi.git`

### Building
#### Windows (Visual Studio)
0) Open command line
1) Navigate to `xash3d-fwgs` directory.
2) Carefully examine which build options are available: `waf --help`
3) Configure build: `waf configure -T release --sdl2=c:/path/to/SDL2`
4) Compile: `waf build`
5) Install: `waf install --destdir=c:/path/to/any/output/directory`

#### Linux
If compiling 32-bit on amd64, you may need to supply `export PKG_CONFIG_PATH=/usr/lib/i386-linux-gnu/pkgconfig` prior to running configure.

0) Examine which build options are available: `./waf --help`
1) Configure build: `./waf configure -T release`
(You need to pass `-8` to compile 64-bit engine on 64-bit x86 processor)
2) Compile: `./waf build`
3) Install(optional): `./waf install --destdir=/path/to/any/output/directory`
