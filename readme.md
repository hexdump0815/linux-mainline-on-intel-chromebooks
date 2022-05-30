# running linux mainline on intel chromebooks

## intro

intel chromebooks are already quite well supported by mainline linux and even linux distributions just like normal intel systems after installing one of the legacy rw or uefi firmware from https://mrchromebox.tech/ - more details about this precedure can be found on this site.

there are still some reasons which might make the bootable images discussed here interesting:

- they are ready to run, i.e. no long and interactive installation procedure required
- they contain a few optimizations for memory and disk size limited systems (which is often the case for chromebooks) like zswap swap and memory compression and the usage of a compressed btrfs filesystem by default
- there is the beginning of support for chromebooks for which there is no extra firmware available yet (like for chromebooks with gemini lake cpus) by using the chromeos native way of booting them and a kernel based on the chromeos kernel sources
- the mbr and uefi images are offered in two versions with 64bit and 32bit userland - the latter might be a good idea for chromebooks with only 2gb of memory as it uses about one third less memory than the 64bit version

a lot of the arm chromebook intro https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks#intro fully or partially also applies here.

## supported devices and linux distributions

currently xubuntu 20.04 (focal) and debian 11 (bullseye) are supported.

the following chromebook types are more or less supported:

- chromebook x86 mbr:
  - in theory it should work for nearly all intel chromebooks with a working legacy rw firmware installed
  - as there are no real chromebook dependency the chance is high that the images should simply work on most intel systems with mbr booting
  - https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_x86_mbr/readme.md
- chromebook x86 uefi:
  - in theory it should work for nearly all intel chromebooks with a working uefi firmware installed
  - as there are no real chromebook dependency the chance is high that the images should simply work on most intel systems with uefi booting with secure boot disabled
  - https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_x86_uefi/readme.md
- chromebook octopus:
  - intel chromebooks with gemini lake socs (i.e. without any legacy or uefi firmware available) using a 4.14 kernel should be working fully or partially as well, maybe others are working too or could be made working this way
  - https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_octopus/readme.md

## enabling developer mode

this is basically the same as for arm chromebooks: https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks#enabling-developer-mode

## setting gbb flags, enabling ccd and the magic suzyqable

this is basically the same as for arm chromebooks: https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks#setting-gbb-flags-enabling-ccd-and-the-magic-suzyqable

## different boot options: mbr, uefi, native

there are three ways to boot intel chromebooks. the first is booting using a traditional mbr based method like it is used also by many older regular intel systems - for this the legacy rw firmware from mrchromebox has to be installed. the second way is based on the more modern uefi method like it is used also by many newer regular intel systems - for this the uefi firmware from mrchromebox has to be installed. the third option is required for chromebooks for which there is neither a legacy rw nor an uefi firmware availabe (yet) and for which thus the tho first options are not possible. this third approach is simaply packaging the linux kernel the same way as it is done for chromeos and boots it in a very similar way as chromeos itself is being booted - for this approach no extra firmware is required, but a special kernel packaged in this special way is required.

## using and adjusting the bootable images

due to the wide variation of hardware some adjustments might be required to get audio, wifi and suspend/resume working porperly on some models, but many intel chromebooks should run out of the box with the mbr or uefi images.

## storing chromebooks and avoiding battery drain

this is basically the same as for arm chromebooks: https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks#storing-chromebooks-and-avoiding-battery-drain

## other related projects

for intel chromebooks:

- https://mrchromebox.tech/
- https://galliumos.org/
- https://github.com/cb-linux/breath
- https://github.com/EMLommers/pixelbook-fedora
- https://github.com/yusefnapora/pixelbook-linux

for arm chromebooks:

- https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks
