# ogNetworkBoot

This repo contains the configuration files to make an custom image using live-build
and the PXE menu to boot that image using live-boot.

## Steps to create the image using Live-Build
1. `mkdir image && cd image`
2. `mkdir auto`
3. `cp ~/auto/config auto/`
4. `lb config`
5. `cp ~/packages/aditionalsoftware.list.chroot config/package-lists/`
6. `cp ~/packages/desktop.list.chroot config/package-lists/`
7. `cp ~/packages/graphics.list.chroot config/package-lists/`
8. `sudo lb build`

When this process is finished, the files needed for the network boot can be found in 
the following directories:

* *filesystem.squashfs*: `~/image/binary/live/filesystem.squashfs`
* *initrd.img*: `~/image/binary/live/initrd.img`
* *vmlinuz*: `~/image/binary/live/vmlinuz`

## Steps to network boot using Live-Boot
1. Make avaliable the filesystem.squashfs file with an http server
2. Change (if necesary) the route to the file in the pxe_menu file
3. Rename the pxe_menu file to the MAC address of the PC to Network Boot
