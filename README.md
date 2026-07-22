# Samsung Galaxy Tab A7 10.4 (SM-T509) - Vendor Tree

## Device specifications

| Feature | Spec |
|---|---|
| Codename | gta4lve |
| Platform | Unisoc UMS512 (sharkl5Pro) |
| Chipset | Unisoc T618 (12nm) |
| Architecture | arm64 |
| Android | 12 (Stock), LineageOS 23 (Target) |

## What's included

| Component | Details |
|---|---|
| Proprietary Blobs | 1547 files from stock firmware dump |
| Vendor Makefile | Complete gta4lve-vendor.mk with PRODUCT_COPY_FILES |
| Android.bp | Soong namespace + VINTF manifests |
| proprietary-files.txt | Full blob list (1547 entries) |
| setup-makefiles.sh | Vendor blob generation script |

## Build instructions

```bash
repo init -u https://github.com/LineageOS/android.git -b lineage-23.2 --depth=1
repo sync -c -j$(nproc --all)

# Clone device trees
git clone https://github.com/Il103/android_device_tree_gta4lve.git device/samsung/gta4lve -b device-lineage-23.2
git clone https://github.com/Il103/android_vendor_tree_gta4lve.git vendor/samsung/gta4lve -b vendor-lineage-23.2
git clone https://github.com/Il103/android_kernel_samsung_gta4lve.git kernel/samsung/gta4lve -b kernel-lineage-23.2

# Build
source build/envsetup.sh
lunch lineage_gta4lve-userdebug
mka bacon -j$(nproc --all)
```

## Blob sources

All blobs extracted from stock firmware:
- **Firmware version**: gta4lvexx-user 12 SP1A.210812.016 T509XXS3AXJ2
- **Source**: Stock firmware dump (1547 proprietary files)
- **Partitions**: system, vendor, product, system_ext

## Status

| Component | Status |
|---|---|
| Blobs extracted | Complete |
| Vendor makefile | Generated |
| VINTF manifests | Included |
| Build tested | Not yet |

## Credits

- [BERU](https://github.com/Il103) for building and maintaining this vendor tree
- LineageOS for the build system
