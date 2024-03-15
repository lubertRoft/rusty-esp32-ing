# Playing with ESP32 and Rust

## Installing the toolchain in Windows 11 on WSL

If you tried to get the toolchain up and running on Windows (I tried 11), better directly switch to WSL (I tried Ubuntu-22.04).

I started here: https://docs.esp-rs.org/book/introduction.html

Just follow the instructions, they are a great start!

1. after installing the toolchains with espup you can directly ```cargo install espflash```
2. also you should ```sudo apt install libudev-dev pkg-config```
3. Install usbipd in windows to be able to flash the microcontroller from within WSL: https://github.com/dorssel/usbipd-win 
4. after attaching the device to WSL I had the problem that, permissions to access the device were denied. Therefore you will need access to the user group, to which the USB device is assigned to. In my case it was root, so I added my user to that group. Unfortunately the udev rules service is not starting at startup of WSL, so you will need set that: https://github.com/microsoft/WSL/issues/8502
5. ... now you should be ready to run ```cargo build``` and ```cargo run``` from the root folder of your template project: https://docs.esp-rs.org/book/writing-your-own-application/generate-project/index.html

I hope that helps someone and good luck!