# signalsdrpi-fw
This is a fork from PlutoSDR Firmware. Pre-compiled binary.

* Build Instructions (Tested on Debian 12)
```bash
sudo apt-get install git build-essential fakeroot libncurses5-dev libssl-dev ccache
sudo apt-get install dfu-util u-boot-tools device-tree-compiler libssl1.0-dev mtools
sudo apt-get install bc python3 cpio zip unzip rsync file wget gcc-arm-linux-gnueabihf
sudo apt-get install libncurses5 device-tree-compiler  u-boot-tools xvfb
git clone --recursive https://github.com/signalens/signalsdrpi-fw
cd signalsdrpi-fw
mkdir -p cd buildroot/output/host
cd buildroot/output/host/
ln -s /tools/Xilinx/Vitis/2023.2/gnu/aarch32/lin/gcc-arm-linux-gnueabi/x86_64-petalinux-linux
cd ../../../
export CROSS_COMPILE=arm-linux-gnueabihf-
export PATH=$PATH:/tools/Xilinx/Vitis/2023.2/gnu/aarch32/lin/gcc-arm-linux-gnueabi/bin
export VIVADO_SETTINGS=/tools/Xilinx/Vivado/2023.2/settings64.sh
export PERL_MM_OPT=
VIVADO_VERSION=v2023.2 FORCE_UNSAFE_CONFIGURE=1 make 
VIVADO_VERSION=v2023.2 FORCE_UNSAFE_CONFIGURE=1 make sdimg
```
