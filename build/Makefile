#!/bin/bash

# Set source and output file paths
SRC="../src/main.asm"
BIN="main.bin"
IMG="main.img"
ISO="main.iso"
BOOT_CAT="boot.cat"
#
# # Assemble the bootloader
nasm -f bin "$SRC" -o "$BIN"
#
# # Create a floppy disk image
dd if="$BIN" of="$IMG" bs=512 count=1 conv=notrunc
#
# # Create a bootable ISO
mkisofs -o "$ISO" -b "$IMG" -c "$BOOT_CAT" -no-emul-boot -boot-load-size 4 -boot-info-table .
#
# # Print success message
echo "ISO created successfully: $ISO"
#
