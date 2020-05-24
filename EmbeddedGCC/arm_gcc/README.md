# GNU MCU Eclipse ARM Embedded GCC

This is the **GNU MCU Eclipse** (formerly GNU ARM Eclipse) version of the 
[GNU Arm Embedded Toolchain](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm).

## Easy install

The **GNU MCU Eclipse ARM Embedded GCC** toolchain is also available as a 
binary [xPack](https://www.npmjs.com/package/@gnu-mcu-eclipse/arm-none-eabi-gcc) 
and can be conveniently installed with [xpm](https://www.npmjs.com/package/xpm):

```console
$ xpm install --global @gnu-mcu-eclipse/arm-none-eabi-gcc
```

For more details on how to install the toolchain, please see 
[How to install the ARM toolchain?](http://gnu-mcu-eclipse.github.io/toolchain/arm/install/) page.

## Compliance

This release closely follows the official ARM distribution, as described 
in the original ARM release text files:

- `gnu-mcu-eclipse/arm-readme.txt`
- `gnu-mcu-eclipse/arm-release.txt`

## Changes

Compared to the ARM distribution, the build procedure is more or less the 
same and there should be no functional differences, except the following 
bug fixes:

- a patch was applied to binutils to fix the 32-bit objcopy bug 
  [24065](https://sourceware.org/bugzilla/show_bug.cgi?id=24065)
- GDB was built the Git commit ad0f979c9 from 2019-01-29, to fix the bugs
  affecting C++ LTO projects
  [24145](https://sourceware.org/bugzilla/show_bug.cgi?id=24145)
- by default, the GCC build script fails to create `liblto_plugin-0.dll`
  for static builds with mingw; code to create the plugin was added
- the `liblto_plugin` copied/linked to the `lib/bdf-plugins` for `ar`
  to find it and be able to process archives with LTO objects
- a patch was applied to gcc to fix the Windows LTO with -g bug
  [89183](https://gcc.gnu.org/bugzilla/show_bug.cgi?id=89183)
- a patch was applied to gcc to fix the Windows paths with spaces bug
  [89249](https://gcc.gnu.org/bugzilla/show_bug.cgi?id=89249)

## Compatibility

The binaries were built using 
[xPack Build Box (XBB)](https://github.com/xpack/xpack-build-box), a set 
of build environments based on slightly older distributions, that should be 
compatible with most recent systems.

- GNU/Linux: all binaries built with GCC 7.2, running in a CentOS 6 
  Docker container
- Windows: all binaries built with mingw-w64 GCC 7.2, running in a 
  CentOS 6 Docker container 
- macOS: all binaries built with GCC 7.2, running in a custom Homebrew 
  instance on macOS 10.10.5

## Build

The scripts used to build this distribution are in:

- `gnu-mcu-eclipse/scripts`

For the prerequisites and more details on the build procedure, please see the 
[How to build the ARM Embedded GCC binaries?](http://gnu-mcu-eclipse.github.io/toolchain/arm/build-procedure/) page. 

## Documentation

The original PDF documentation is available in:

- `share/doc/pdf`

## More info

For more info and support, please see the GNU MCU Eclipse project site:

http://gnu-mcu-eclipse.github.io


Thank you for using **GNU MCU Eclipse**,

Liviu Ionescu


