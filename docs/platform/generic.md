Generic Platform
================

The **Generic** platform is a flattened device tree (FDT) based platform
where all platform specific functionality is provided based on FDT passed
by previous booting stage. The **Generic** platform allows us to use same
OpenSBI firmware binaries on various emulators, simulators, FPGAs, and
boards.

By default, the generic FDT platform makes following assumptions:

1. platform FW_TEXT_START is 0x80000000
2. platform features are default
3. platform stack size is default
4. platform has no quirks or work-arounds

The above assumptions (except 1) can be overridden by adding special platform
callbacks which will be called based on FDT root node compatible string.

Users of the generic FDT platform will have to ensure that:

1. Various FDT based drivers under lib/utils directory are upto date
   based on their platform requirements
2. The FDT passed by previous booting stage has DT compatible strings and
   DT properties in sync with the FDT based drivers under lib/utils directory

To build the platform-specific library and firmware images, provide the
*PLATFORM=generic* parameter to the top level `make` command.

For custom FW_TEXT_START, we can build the platform-specific library and
firmware images by passing *PLATFORM=generic FW_TEXT_START=<custom_text_start>*
parameter to the top level `make` command.

Platform Options
----------------

The *Generic* platform does not have any platform-specific options.

RISC-V Platforms Using Generic Platform
---------------------------------------

To be added later.
