# BC2VR — Singleplayer Pre-alpha

> **Experimental pre-alpha. Knife interaction has failed current headset testing,
> and death/reload crashes remain unresolved.** Opening-guard progression and a
> complete campaign have not passed acceptance. Multiplayer is unsupported.

An experimental VR mod for **Battlefield: Bad Company 2**, built on [FrostbiteVR](https://github.com/justiceofrip/FrostbiteVR). This separate repository provides the installer, updates and feedback tracker.

**0.1.11 fixes asset preparation when a dedicated `BC2VR-Launcher` folder is inside the game installation.** Native binaries and gameplay remain exactly those of 0.1.10. The cache-path checks and fresh-install, update and rollback checks passed.

## Install and play

You need 64-bit Windows, your own supported BC2 installation, Direct3D 11 and a working OpenXR headset with motion controllers. Connect your headset through your preferred PC streaming app and select its OpenXR runtime. SteamVR is the current tested headset setup. Install on a local fixed drive of your choice, including C:; the launcher checks the space needed and keeps temporary files with the installation.

1. Download **BC2VR-Setup-0.1.11.zip** from [Releases](https://github.com/justiceofrip/BC2VR/releases).
2. Extract it, keep the inner **BC2VR-0.1.11-win64.zip** intact, and run **Install.cmd**. First setup needs internet access for portable dependencies.
3. Open the **BC2 VR** desktop shortcut, use **Choose game folder** to select `BFBC2Game.exe`, connect your headset and select **Launch BC2 in VR**.
4. Choose your campaign in the VR menu. Point with the right controller and select with its trigger.

First launch prepares equipment and audio caches from your installed game. Python is bundled; the first asset preparation downloads a pinned FFmpeg audio decoder (about 77 MB) directly from its upstream GitHub release. Validation and launches with a complete asset cache do not download it. No game executable, assets or saves are distributed. The launcher checks the supported executable and selected OpenXR runtime before starting. An unverified build is reported with a fingerprint for feedback; this is not blanket support for every EA, Steam or retail executable. The launcher does not change your OpenXR runtime or game settings. **Stop VR** ends the mod session and leaves BC2 and your VR software open.

## Startup help

The chosen game path is shown above Launch. If settings cannot be read, use the offered recovery action; the original file is backed up before repair or reset.

If the Direct3D 11 check fails, close BC2 and select `DxVersion=11` in its `Documents/BFBC2/settings.ini`, then retry. Keep the headset connected while the game reaches its main menu. Startup reports progress and waits for native VR input telemetry; it does not claim success merely because the game process opened. Use **Report feedback → Save diagnostics** when a check fails.

If VR stops while BC2 remains open, select **Restart BC2 before launch**, or close BC2 normally and launch again. Wait for any cleanup message to finish. **You do not need to delete or reinstall BC2VR.** The desktop game resolution does not need to be 16:9 for menu pointing.

If 0.1.10 reports **“Generated assets must not be written into the game installation”**, the launcher may be installed below the game folder. Update to 0.1.11, which permits its dedicated managed cache there. Installing the launcher directly into the game root or its stock `Dist`/`Package` folders remains unsupported. **You do not need to reinstall the game.**

## Controls and updates

Move with the left stick, snap turn with the right stick, fire with the right trigger, and use grips for supported weapon handling. Hold both stick clicks for one second to recenter. Open the pause menu with the left menu button; X+Y held for half a second is the fallback when the runtime reserves that button.

Close BC2 before selecting **Check for updates** and **Install update**. Keep **Include pre-alpha hotfixes** enabled. Settings and one previous package are retained; **Roll back** selects that previous version.

**If the launcher reports a damaged package or an older updater cannot continue:** download the new Setup, run **Install.cmd**, and choose your **existing launcher folder containing `active.json`**. Repair replaces a damaged copy only after the replacement is fully verified, preserving your settings and a verified previous version.

The 0.1.11 update preserves settings and a previous package for rollback. The changed preparation recipe may require a new local asset cache on the next launch.

## What to expect

The mod includes native stereo, tracked weapons and support hands, roomscale movement, physical equipment handling and manual reloads for supported weapons. The opening cloud correction has passed a headset check. Checkpoint 426 adds measured Nambu100 grip/aim data and native manual-magazine evidence.

Knife interaction has failed current headset testing. Earlier damage checks with emulated controller input did not establish working headset knife handling or opening-mission progression. The 0.1.11 cache fix does not change native gameplay or resolve those failures.

Death/reload crashes have no accepted fix. Nambu downstream launch and impact alignment remain unverified; the recenter correction still needs a headset check. Extended play, reconnects, unsupported weapons, manual LMG reloads and some magnified scopes remain unfinished.

The included 0.1.8 startup fix removes a development-machine drive restriction from the native audio-cache readers. A tester's valid X: installation was rejected during VR startup; both readers now accept validated absolute local paths on the player's selected drive. Required audio hashes and formats remain checked. Startup and saved diagnostics also show the underlying native failure reason when available, rather than only `probe_exit:20`.

Installer/update tests simulate different folder layouts and runtime selections; they do not emulate another GPU, headset connection or store executable. Actual EA/VDXR headset rendering remains unverified. The previous package-repair and per-resource preparation checks remain included.

## Feedback

Use **Report feedback** in the launcher or [open an issue](https://github.com/justiceofrip/BC2VR/issues/new/choose). Include your headset/connection, version, mission, weapon and reproduction steps.

The launcher can prepare a small diagnostics ZIP from bounded text logs and build details. Review **Report.txt** before attaching it yourself. Nothing uploads automatically; game assets, settings, screenshots and memory dumps are excluded. Short videos with timestamps are useful for visual or interaction problems.

This is an unofficial community mod. Framework source and development are in [FrostbiteVR](https://github.com/justiceofrip/FrostbiteVR).
