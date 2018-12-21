# Overview

This is a let's split keyboard firmware based on the [tmk\_keyboard firmware](http://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers.

## Build environment (Ubuntu)

$sudo apt-get install gcc unzip wget zip gcc-avr binutils-avr avr-libc dfu-programmer dfu-util gcc-arm-none-eabi binutils-arm-none-eabi libnewlib-arm-none-eabi

## How to build

Clone this source code to your PC.  

$git clone https://github.com/staka1126/lets_split.git  
$cd lets_split/keyboards/lets_split/keymaps/default  
$make  

And you can get a firmware file named "lets_split_rev2_default.hex" on .build directory.  

## flush your firmware

(Ubuntu)  
$sudo make avrdude
  ---> reset

(Windows)  
https://gist.github.com/CampAsAChamp/e747d2b605c0c32923593b529f82ccdd

## How to write EEPROM (Once)

you can get eeprom files on ./quantum/keyboards/lets_split.

If this is the first time you’re flashing the boards, you have to flash EEPROM

1. If your keyboard is plugged in, unplug it
2. Open a terminal, and navigate to the qmk_firmware folder
3. Run "ls /dev | grep tty" Note down which ports you see
4. Plug the keyboard in, if it’s new, it should enter bootloader, if it’s not new, see Entering bootloader on how to enter bootloader mode
5. Right after entering bootloader, run "ls /dev | grep tty" again. There should be a new tty, this is the bootloader TTY, note it down. 6. If nothing shows see Entering bootloader on how to enter bootloader mode
7. For the left hand side, run "avrdude -c avr109 -p m32u4 -P /dev/ttyS1 -U eeprom:w:"./quantum/split_common/eeprom-lefthand.eep":a" Replace /dev/ttyS1 with the port you noted down earlier. If you’re on windows using msys2, replace /dev/ttyS1 with COM2, note that the number is one higher than the tty number.
8. Do the same For the right hand, but change the file to eeprom-righthand.eep

## Change keymaps from original (default)
* Activate LED control keys to Adjust layer
* Swap ESC and Ctrl
* Assign Home, End, PageUp/Down, PrintScreen to Lower layer
* Assign Caps to Raise layer
* Delete COLEMAK, DVORAK layers

## Documentation

[https://docs.qmk.fm](https://docs.qmk.fm) is hosted on [Gitbook](https://www.gitbook.com/book/qmk/firmware/details).
