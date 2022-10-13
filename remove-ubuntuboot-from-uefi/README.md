# Remove Ubuntu Boot from UEFI during boot

To remove you must have a Ubuntu in pen-drive or CD/DVD

Insert your disk and enter in `Try or Install Ubuntu`

Follow this instructions:

1. Open terminal (CTRL + ALT +T)
2. Type `sudo efibootmgr`, if dont exists, install with `sudo apt install efibootmgr`.
3. Find Ubuntu in menu and note down its boot number e.g. `1` for `Boot0001`
4. Type `sudo efibootmgr -b BOOT_NUMBER -B` to delete entry from Boot Menu.

-b -> modify boot number

-B -> delete boot number