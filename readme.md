# Overview

This is a let's split keyboard firmware based on the [tmk\_keyboard firmware](http://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers.

## Official website

[http://qmk.fm](http://qmk.fm) is the official website of QMK, where you can find links to this page, the documentation, and the keyboards supported by QMK.

## Build environment (Ubuntu)

$sudo apt-get install gcc unzip wget zip gcc-avr binutils-avr avr-libc dfu-programmer dfu-util gcc-arm-none-eabi binutils-arm-none-eabi libnewlib-arm-none-eabi

## How to build

Clone this source code to your PC.  

$git clone https://github.com/staka1126/lets_split.git  
$cd lets_split/keyboards/lets_split/keymaps/default  
$make  

And you can get a firmware file named "lets_split_rev2_default.hex" on .build directory.  

## How to write EEPROM (Once)

https://leico.github.io/TechnicalNote/QMK/write-vitamins-avrdude


## How to flash firmware

(Ubuntu)  
$sudo make avrdude
  ---> reset

(Windows)  
https://gist.github.com/CampAsAChamp/e747d2b605c0c32923593b529f82ccdd

you can get eeprom files on ./keyboards/lets_split.

## Change keymaps from original (default)
* Activate LED control keys to Adjust layer
* Swap ESC and Ctrl
* Assign Home, End, PageUp/Down, PrintScreen to Lower layer
* Assign Caps to Raise layer
* Delete COLEMAK, DVORAK layers

## Documentation

[https://docs.qmk.fm](https://docs.qmk.fm) is hosted on [Gitbook](https://www.gitbook.com/book/qmk/firmware/details).
