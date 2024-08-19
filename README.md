# signalsdrpi-fw-bin
Precompile binary from https://github.com/signalens/signalsdrpi-fw This is a fork from PlutoSDR Firmware. 

* Build Instructions
```bash
sudo apt-get install git build-essential fakeroot libncurses5-dev libssl-dev ccache
sudo apt-get install dfu-util u-boot-tools device-tree-compiler libssl1.0-dev mtools
sudo apt-get install bc python cpio zip unzip rsync file wget
git clone --recursive https://github.com/signalens/signalsdrpi-fw
export CROSS_COMPILE=arm-linux-gnueabihf-
export PATH=$PATH:/tools/Xilinx/SDK/2019.1/gnu/aarch32/lin/gcc-arm-linux-gnueabi/bin
export VIVADO_SETTINGS=/tools/Xilinx/Vivado/2019.1/settings64.sh
export PERL_MM_OPT=
cd signalsdrpi-fw
make
make sdimg
```