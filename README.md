# android_device_xiaomi_raphael
For building TWRP for Xiaomi Redmi K20 Pro

TWRP device tree for Xiaomi Redmi K20 Pro

## Features

Works:

- ADB
- Decryption of /data (Only if pattern or pin or password is not setted)
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/raphael" name="mauronofrio/android_device_xiaomi_raphael" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_raphael-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/raphael/recovery.img
```

## Other Sources

Kernel Sources: https://github.com/acervenky/raphaelquax

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
