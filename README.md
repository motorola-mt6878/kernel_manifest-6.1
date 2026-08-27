nice kernel building
===========

Getting started
---------------

To get started with Android, you'll need to get familiar with [Source Control Tools](https://source.android.com/setup/develop).

To initialize your local repository using the Google kernel manifest, use a command like this:
```
repo init -u https://android.googlesource.com/kernel/manifest.git -b common-android14-6.1-lts --depth=1
```
Then use a command like this to clone the local manifest at the root of your local repository:
```
git clone https://github.com/motorola-mt6878/kernel_manifest-6.1.git .repo/local_manifests
```
Then to sync up:
```
repo sync
```

Building the kernel
-------------------
To build the GKI kernel image and the device kernel modules, use a command like this at the root of your local repository:
```
DEFCONFIG_OVERLAYS=ext_config/moto-mgk_64_k61-nice.config MODE=user ./kernel_device_modules-6.1/build.sh
```
Then every built artifacts are available at:
```
out/dist/
```

Updating the prebuilt kernel repository
---------------------------------------
To update the [prebuilt kernel repository](https://github.com/motorola-mt6878/device_motorola_nice-kernel.git), use the [copy script](https://gist.github.com/rio004/cd128f3c187dfa42f4f27f7f4fd385aa) in prebuilt kernel repository and find any missing files manually if needed.
