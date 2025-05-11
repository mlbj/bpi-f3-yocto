# bpi-f3-yocto

This project builds a minimal Yocto-based Linux image for the Banana Pi F3.

## Cloning the Repository

To clone this repository along with its submodules, use the following command:

```bash
git clone --recurse-submodules https://github.com/mlbj/bpi-f3-yocto
```

If you have already cloned the repository without submodules, initialize them with:

```bash
git submodule update --init --recursive
``` 

## Build Instructions

To build the image, simply run:

```bash
source poky/oe-init-build-env build
bitbake bananapi-f3-image
```

## Flashing the Image

After building, the resulting image `sdcard.img` will be available in:

```
build/tmp/deploy/images/bananapi-f3/
```

Use `dd` to flash it to an SD card:

```bash
sudo dd if=build/tmp/deploy/images/bananapi-f3/sdcard.img of=/dev/sdX bs=4M status=progress
```

Replace `/dev/sdX` with the appropriate device path.

## License

This project is licensed under the MIT License.


