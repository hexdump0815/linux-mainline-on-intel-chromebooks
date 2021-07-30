# running linux mainline on intel chromebooks

## intro

coming soon ...

## supported devices and linux distributions

currently xubuntu 20.04 (focal) is supported and debian 11 (bullseye) is planned to be supported a bit after it is officially released.

the following chromebook types are more or less supported:

- chromebook x86 mbr:
  - in theory it should work for nearly all intel chromebooks with a working legacy rw firmware installed
  - as there are no real chromebook dependency the chance is high that the images should simply work on most intel systems with mbr booting
  - https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_x86_mbr/readme.md
- chromebook x86 uefi:
  - in theory it should work for nearly all intel chromebooks with a working uefi firmware installed
  - as there are no real chromebook dependency the chance is high that the images should simply work on most intel systems with uefi booting with secure boot disabled
  - https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_x86_uefi/readme.md
- chromebook x86 native chromeos boot:
  - intel chromebooks with gemini lake socs (i.e. without any legacy or uefi firmware available) using a 4.14 kernel might be working fully or partially as well, maybe others are working too or could be made working this way
  - https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_x86_native/readme.md

## enabling developer mode

this is basically the same as for arm chromebooks: https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks#enabling-developer-mode

## setting gbb flags, enabling ccd and the magic suzyqable

this is basically the same as for arm chromebooks: https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks#setting-gbb-flags-enabling-ccd-and-the-magic-suzyqable

## different boot options: mbr, uefi, native

coming soon ...

## using and adjusting the bootable images

coming soon ...

## other related projects

for intel chromebooks:

- https://mrchromebox.tech/
- https://galliumos.org/

for arm chromebooks:

- https://github.com/hexdump0815/linux-mainline-on-arm-chromebooks
