* hexファイルの作り方
```
$ sudo apt-get install gcc-avr avr-libc dfu-programmer
$ git clone https://github.com/jackhumbert/qmk_firmware.git
$ cd ./qmk_firmware/keyboards/ergodox_ez
$ vim keymaps/default/keymap.c
$ make
```
これでkeymap.cからergodox_ez_default.hexが生成される