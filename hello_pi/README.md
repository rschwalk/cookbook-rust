# cookbook-rust hello_pi
cross compileing example for the raspberry pi

## Setup the cross compiling envireonment
* install rust cross compile create for ARMv7
```bash
rustup target add armv7-unknown-linux-gnueabihf
```
* clone the ARM compiler from the raspberry tools git repo
```bash
git clone --depth=1 https://github.com/raspberrypi/tools.git tools
```
* add to the PATH or simlink to _/usr/bin_
```bash
export PATH=tools/arm-bcm2708/arm-linux-gnueabihf/bin:$PATH
```
__OR__
```bash
sudo ln -s [your home dir with full path]/tools/arm-bcm2708/arm-linux-gnueabihf/bin/* /usr/bin/
```
* configure cargo for the target, for the project in the project directory or in the home directory for global use: add the folowing lines to _.cargo/config_
```
[target.armv7-unknown-linux-gnueabihf]
linker = "arm-linux-gnueabihf-gcc"
```
* build the program with cargo
```bash
cargo build --target=arm-unknown-linux-gnueabihf
```
