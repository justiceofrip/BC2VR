# BC2VR — Singleplayer Pre-alpha

An experimental VR mod for **Battlefield: Bad Company 2**, built on [FrostbiteVR](https://github.com/justiceofrip/FrostbiteVR). This separate repository provides the installer, updates and feedback tracker.

**0.1.5 / checkpoint 426 is an experimental pre-alpha.** Opening-knife combat is unresolved and can block progress in the first mission. Crashes after deaths/reloads also remain unresolved. A complete campaign and every weapon have not been verified. Multiplayer is unsupported.

## Install and play

You need 64-bit Windows, your own supported BC2 installation, Direct3D 11 and a working OpenXR headset with motion controllers. SteamVR is the current testing setup. Use a data drive with at least 16 GiB free; installation and temporary files stay there.

1. Download **BC2VR-Setup-0.1.5.zip** from [Releases](https://github.com/justiceofrip/BC2VR/releases).
2. Extract it, keep the inner **BC2VR-0.1.5-win64.zip** intact, and run **Install.cmd**. First setup needs internet access for portable dependencies.
3. Open the **BC2 VR** desktop shortcut, choose your BC2 installation, connect your headset and select **Launch BC2 in VR**.
4. Choose your campaign in the VR menu. Point with the right controller and select with its trigger.

First launch prepares equipment and audio caches from your installed game. Python is bundled; the first asset preparation downloads a pinned FFmpeg audio decoder (about 77 MB) directly from its upstream GitHub release. Validation and launches with a complete asset cache do not download it. No game executable, assets or saves are distributed. The launcher checks the supported executable before starting. **Stop VR** ends the mod session and leaves BC2 and SteamVR open.

## Controls and updates

Move with the left stick, snap turn with the right stick, fire with the right trigger, and use grips for supported weapon handling. Hold both stick clicks for one second to recenter. Open the pause menu with the left menu button; X+Y held for half a second is the fallback when the runtime reserves that button.

Close BC2 before selecting **Check for updates** and **Install update**. Keep **Include pre-alpha hotfixes** enabled. Settings and one previous package are retained; **Roll back** selects that previous version.

## What to expect

The mod includes native stereo, tracked weapons and support hands, roomscale movement, physical equipment handling and manual reloads for supported weapons. The opening cloud correction has passed a headset check. Checkpoint 426 adds measured Nambu100 grip/aim data and native manual-magazine evidence.

The opening knife can render and start an attack, but repeat stabbing, enemy damage and mission progression are not verified. Some players may be unable to continue past the opening combat. The death/reload crash has no accepted fix. Nambu impact alignment and the recenter correction still need headset verification. Extended play, reconnects, unsupported weapons, manual LMG reloads and some magnified scopes remain unfinished.

The release package passed fresh-install, update, rollback, feedback and corrupt-package rejection checks. These packaging checks do not establish campaign playability.

## Feedback

Use **Report feedback** in the launcher or [open an issue](https://github.com/justiceofrip/BC2VR/issues/new/choose). Include your headset/connection, version, mission, weapon and reproduction steps.

The launcher can prepare a small diagnostics ZIP from bounded text logs and build details. Review **Report.txt** before attaching it yourself. Nothing uploads automatically; game assets, settings, screenshots and memory dumps are excluded. Short videos with timestamps are useful for visual or interaction problems.

This is an unofficial community mod. Framework source and development are in [FrostbiteVR](https://github.com/justiceofrip/FrostbiteVR).
