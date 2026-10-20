# AOSPAAsteroids manifest (android-17 / QSI volcano bring-up)

This manifest revision is 100% asteroids-compatible: it pins the platform
and all ROM-specific trees to `fruity-aospa` — including the device tree,
blobs, sm7635 kernel (+modules, devicetrees) and Dolby — so one sync is
enough, no local_manifest needed.

## Sync

    repo init -u https://github.com/fruity-aospa/manifest.git -b asteroids
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
