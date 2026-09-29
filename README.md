# RisingOS Revived 9 for Samsung Galaxy A6 (2018)

This repository contains the pinned source overrides used for the Android 17
`a6lte` port. The tested model is SM-A600FN.

The local manifest pins every device-specific or modified project to an exact
commit. Projects that are not overridden continue to come from the RisingOS
Revived `seventeen` manifest.

## Source checkout

```bash
mkdir -p ~/android/rising-a6lte
cd ~/android/rising-a6lte

repo init -u https://github.com/RisingOS-Revived/android.git \
  -b seventeen --git-lfs

mkdir -p .repo/local_manifests
curl -L \
  https://raw.githubusercontent.com/Kejlo523/risingos9-a6lte-sources/main/a6lte.xml \
  -o .repo/local_manifests/a6lte.xml

repo sync -c --force-sync --no-clone-bundle --no-tags -j4
```

`-j4` is a conservative sync setting. It may be increased on a host with ample
RAM and reliable storage/network access.

## Build

Android's checked-out prebuilt JDK 21 is selected by `envsetup.sh`; do not set
an unrelated system `JAVA_HOME`.

```bash
cd ~/android/rising-a6lte
unset JAVA_HOME ANDROID_JAVA_HOME
source build/envsetup.sh

export BUILD_USERNAME=Kejlo
export BUILD_HOSTNAME=endozero

lunch lineage_a6lte-userdebug
m bacon
```

Use `m bacon`, not a standalone `bacon` command. The product configuration is
set to the CORE/pico GApps variant because the full GApps set does not fit the
device's fixed 4 GiB system partition.

Do not delete `out` when resuming an interrupted build. Running `m bacon` again
reuses valid completed outputs.

## Important status note

The source set contains the live-tested device fixes plus the final eBPF/netd
and CORE GApps integration. Those last source-only commits still require one
final clean-flash validation before publishing an XDA release.

The bundled kernel source is public here:

https://github.com/Kejlo523/android_kernel_samsung_exynos7870/tree/rising-17-a6lte

The XDA-ready draft is in [`XDA_THREAD_DRAFT.md`](XDA_THREAD_DRAFT.md). Do not
post it until direct ROM/recovery download links and screenshots are added.
