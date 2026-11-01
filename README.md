# AOSPAAsteroids manifest (android-17 / 6.1 kernel)

This manifest revision is 100% asteroids-compatible: it pins the platform
and all ROM-specific trees to `fruity-aospa` — including the device tree,
blobs, sm7635 kernel (+modules, devicetrees) and Dolby — so one sync is
enough, no local_manifest needed.

## Sync

    repo init -u https://github.com/fruity-aospa/manifest.git -b calcite-6.1
    repo sync

## Notes

- Base platform comes from AOSP/CLO/AOSPA remotes declared by this
  manifest (android-17.0.0_r1 / AOSPA calcite).
- The `fru` remote (revision `asteroids`) overlays 15 projects: the
  unsigned bring-up fixes (build/soong, external/dtc, wlan, kernelscripts,
  hardware lineage compat, devicesettings, vendor aospa/common/power/
  core-utils-vendor/recovery-ext) and the asteroids device trees
  (device vendor blobs, hardware/nothing, kernel sm7635 family, dolby).
- Do NOT add the old asteroids.xml local_manifest on top of this — the
  projects are declared here and would duplicate.

## calcite-6.1

- Device, blobs, hardware/nothing and the sm7635 kernel family track
  `calcite-6.1` (kernel 6.1 stack on C5.0 blobs).
- Nothing Camera lives in `hardware/nothing/camera` (git-lfs).
