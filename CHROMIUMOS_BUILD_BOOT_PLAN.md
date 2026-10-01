# ChromiumOS Build & Boot Plan

## Purpose
Convert the Chromium Edition from documented integration into a bootable, evidenced artifact.

## Evidence state
- Architecture/integration: PASS within documented scope
- Kernel diligence pin: 0d0ae41f78e3f23da073390285d401c4a215dc6a
- x86-64 build: PENDING
- Boot: PENDING
- Runtime validation: PENDING
- Verified boot: PENDING

## Build host gate
1. Native x86-64 Linux host.
2. Sufficient CPU, RAM, disk, and network for ChromiumOS.
3. Supported ChromiumOS toolchain executes successfully.
4. ARM64 Android/Termux is not the ChromiumOS build host.

## Provenance gate
Record the cranium-boot-drive commit, ChromiumOS manifest revision/hash, Kernel pin, Commander and AI revisions, build log, and artifact SHA256.

## Build sequence
1. Sync ChromiumOS.
2. Confirm board target: amd64-generic.
3. Stage Commander, AI, Wyl assets, and private overlay.
4. Run cros build-packages.
5. Build the test image.
6. Hash the exact image and preserve the log.

## Boot sequence
1. Isolate emulator or supported test machine.
2. Record firmware/emulation configuration.
3. Boot the exact hashed artifact.
4. Capture console/system logs.
5. Verify first boot and Commander.
6. Verify Wyl is guide/host, never authority.
7. Verify consequential actions remain Kernel-governed.

## Acceptance
Build acceptance requires an image, SHA256, source revision, Kernel pin, and successful build exit. Boot acceptance requires the exact recorded image to boot with observable required surfaces.

Failed builds/boots remain failed. New fixes require new evidence.

## Final gate
Do not declare material verification until build, boot, runtime, and verified-boot evidence are independently recorded.
