## Building Lotus

Lotus can be made on pretty much any operating system.

Dependencies are standard, and are the default for QEMU.

For Debian based systems:

```shell
sudo apt-get install git libglib2.0-dev libfdt-dev libpixman-1-dev zlib1g-dev ninja-build
```

For Red-Hat based systems:

```shell
yum install git glib2-devel libfdt-devel pixman-devel zlib-devel bzip2 ninja-build python3
```

### Recommended packages **Optional**

 - `git-email` - Used for sending patches
 - `libsdl1.2-dev` - Needed for the SDL based GUI
 - `gtk3-devel` - For a simple UI (instead of VNC)
 - `vte-devel` - For access to LOTUS Monitor & Serial/Console devices via GTK

For Debian based systems:

 ```shell
sudo apt-get install git-email
sudo apt-get install libaio-dev libbluetooth-dev libbrlapi-dev libbz2-dev
sudo apt-get install libcap-ng-dev libcurl4-gnutls-dev libgtk-3-dev
sudo apt-get install libibverbs-dev libjpeg8-dev libncurses5-dev libnuma-dev
sudo apt-get install librbd-dev librdmacm-dev
sudo apt-get install libsasl2-dev libsdl2-dev libseccomp-dev libsnappy-dev libssh-dev
sudo apt-get install libvde-dev libvdeplug-dev libvte-2.91-dev libxen-dev liblzo2-dev
sudo apt-get install valgrind xfslibs-dev
sudo apt-get install libnfs-dev libiscsi-dev
```

For Red-Hat based systems:

```shell
sudo yum install libaio-devel libcap-ng-devel libiscsi-devel
```

### SUSE-based Distros

The following command line will provide conditions for building QEMU using its default compiler gcc:

```shell
sudo zypper install git-core gcc-c++ make qemu glib2-devel libpixman-1-0-devel
```

To build Lotus via Clang:

```shell
sudo zypper install clang
```

For additional debugging tools:

```shell
sudo zypper install perf valgrind
```

### Darwin Building (macOS)

Setup is simple, main system requirements are:

 - One of the two most recent versions of macOS
 - Clang

To install additional build requirements, use the Homebrew package manager and run:

```shell
brew install libffi gettext glib pkg-config autoconf automake pixman ninja
```

## Building Lotus

Building Lotus is simple, following these instructions. Note: Make sure the above steps have been completed.

Setting up Lotus is as following (universally on any system):

```shell
mkdir -p build
cd build
../configure --target-list=x86_64-softmmu --enable-debug
make all -j$(nproc)
```

And then to install Lotus automatically to PATH

```shell
sudo make install
```

After this, you can run Lotus via the use of `lotus-system-<system-architecture-here>`
