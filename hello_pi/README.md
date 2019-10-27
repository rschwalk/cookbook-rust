# cookbook-rust hello_pi
cross compileing example for the raspberry pi

## Setup the cross compiling envireonment
* install rust cross compile create for ARMv7
```bash
rustup target add armv7-unknown-linux-gnueabihf
```
* clone the ARM compiler from the raspberry tools git repo
* add to the PATH
```bash
git clone --depth=1 https://github.com/raspberrypi/tools.git /tmp/tools
export PATH=/tmp/tools/arm-bcm2708/arm-linux-gnueabihf/bin:$PATH
```
* configure cargo for the target for the projekt int he main directory or in home directory for global use: add the folowing lines to .cargo/config
```
[target.armv7-unknown-linux-gnueabihf]
linker = "arm-linux-gnueabihf-gcc"
```
* build the program with cargo
```bash
cargo build --target=arm-unknown-linux-gnueabihf
```
