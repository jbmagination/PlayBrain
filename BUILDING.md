To build PlayBrain, you must first have a copy of devkitPro: http://sourceforge.net/projects/devkitpro

Install the `wii-dev` and `ppc-minixml` packages. Confirm that `elf2dol` exists by typing `elf2dol` in your terminal.
Also type `powerpc-eabi-g++` and make sure that compiler works.

Set up your PATH so that those packages are usable if they're not found.

In the root directory of the PlayBrain repository, run the commands:
    make

The channel will be generated as `boot.elf` and `boot.dol` in the `bin`
subdirectory. Temporary working files will be places in the `build`
subdirectory. `boot.map`, a symbol map, will also be generated.

To make a release you can run
    make release

This will construct the folder structure that should be put on the SD card
suitable for distribution to end users. You can specify `RELEASE=dir` to release
to a specific directory, but the default directory name is `release`.

To improve the build time, the `-j` flag can be added to the `make` command to parallelise the build.

The optional `DEBUG=1` flag can be added on the end of the `make` command in order to enable debugging assertions in the code.

An assembly code listing can be generated with:
    make list

To delete generated files run:
    make clean
