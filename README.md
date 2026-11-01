# Saiyan007

A patch for **Shima: Dynamic Island** (`com.piyush.island`), compatible with
**Morphe Patcher 2.1.0**.

- Unlocks Pro alerts, gesture rules, swipe gestures, the secondary pill, and backups.
- Includes the **Google Play installer-source fix** automatically.
- Targets **any Shima version** whose bytecode matches the patch fingerprints.

## Use

1. Download `Saiyan007-1.1.0.mpp` from [Releases](https://github.com/AsrOfficialDev/Saiyan007/releases/latest).
2. Load the bundle in Morphe and select your original Shima APK or XAPK.
3. Select **Saiyan007** and patch.

Morphe merges XAPK splits when necessary. The installer fix is included in
Saiyan007; it uses the behavior of **Change installer source → Google Play**.

## Build on Windows

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\build-local.ps1
```

Output: `patches/build/libs/Saiyan007-1.1.0.mpp`.

The build downloads checksum-verified public releases of Java, Kotlin, Morphe
Desktop, and D8. GitHub Packages credentials are not required. Build tools are
cached in `%LOCALAPPDATA%\Temp\Saiyan007\build-tools`.

The bundle contains both JVM classes and Android DEX. Its version is stored in
`gradle.properties`; the standalone script is the build entry point.

## Verification

Build, patch application, APK signature, and bytecode checks passed using
**Shima 0.4.0 (version code 7)**. Other versions have not been verified, and an
incompatible bytecode layout will produce a patching error. The rebuilt APK has
not been tested on a device.

## License and attribution

See [LICENSE](LICENSE) and [NOTICE](NOTICE) for the GPLv3 license and additional terms.

The project originated from the
[Morphe patches template](https://github.com/MorpheApp/morphe-patches-template).
The installer-source implementation is adapted from the
[Morphe patches library](https://github.com/MorpheApp/morphe-patches-library/blob/main/patch-library/src/main/kotlin/app/morphe/patches/all/misc/fix/changepackageinstaller/ChangePackageInstallerPatch.kt).
Saiyan007 is an independently named custom patch project.
