# dali kernel tree (Redmi K80 Ultra / MT6991)

A single Linux 6.6 kernel tree for the Xiaomi Redmi K80 Ultra (codename
`dali`, SoC MT6991), assembled from the repositories MiCode publishes
separately and merged with the Google Android Common Kernel.

## Provenance

| MiCode repository | Branch | Merged as |
|---|---|---|
| Xiaomi_Kernel_OpenSource | bsp-dali-v-oss, f089d58 "dali open source" (Linux 6.6.56) | base tree |
| MTK_kernel_device_modules | bsp-dali-v-oss | merged into the tree root |
| MTK_kernel_modules | bsp-dali-v-oss | merged into `drivers/misc/mediatek/` and `drivers/gpu/mediatek/` |
| kernel_build | bsp-dali-v-oss | AOSP kernel build scripts, kept outside this repo |

The Google Android Common Kernel `android15-6.6` branch (448c303366,
Linux 6.6.142) is merged on top of the base tree, so this tree is based
on Linux 6.6.142.

## Building

Use the AOSP kernel build scripts from `kernel_build` together with the
`build.config.xiaomi.dali` in this repo:

    BUILD_CONFIG=build.config.xiaomi.dali <kernel_build>/build/build.sh

That config merges `arch/arm64/configs/gki_defconfig` with
`arch/arm64/configs/vendor/xiaomi_mt6991.config` and
`arch/arm64/configs/vendor/dali.config`, and builds `Image.gz` and
`mediatek/dali.dtb`.

The prebuilt toolchain (`prebuilts/clang`, `prebuilts/build-tools`,
`prebuilts/gcc`, `prebuilts/jdk`) is not shipped here. Take it from the
AOSP `common-android15-6.6` manifest.

## Status

Not build tested. Two known gaps remain:

  - some Kconfig symbols referenced by the vendor config fragments have no
    definition, because MTK did not open-source those parts;
  - the Kbuild wiring for the merged MTK trees is incomplete.

## Patches

This is a vendor tree, not an upstream kernel; nothing here is submitted
upstream. If you send a change, keep the kernel commit style: English, an
imperative subject line, a body that explains why the change is needed,
and a `Signed-off-by:` tag.
