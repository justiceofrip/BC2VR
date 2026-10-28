# BC2VR — Singleplayer Pre-alpha

> **Experimental pre-alpha.** Testers have played the opening encounter in a headset
> with knife use and manual reloads. A complete campaign has not passed acceptance.
> Vehicles, destruction rendering and death/reload crashes remain unresolved.
> Multiplayer is unsupported.

An experimental VR mod for **Battlefield: Bad Company 2**, built on
[FrostbiteVR](https://github.com/justiceofrip/FrostbiteVR). This repository holds the
installer, updates and feedback tracker. What changed in each version is on the
[Releases](https://github.com/justiceofrip/BC2VR/releases) page.

## Requirements

- 64-bit Windows and your own supported BC2 installation, running Direct3D 11.
- An OpenXR headset with motion controllers, connected through your PC streaming app.
  SteamVR is the tested setup; a tester also reports play through Virtual Desktop/VDXR,
  with low performance.
- A local fixed drive of your choice, including C:. The launcher checks the space it
  needs and keeps temporary files with the installation.

## Install and play

1. Download the latest **BC2VR-Setup** zip from
   [Releases](https://github.com/justiceofrip/BC2VR/releases).
2. Extract it, keep the inner **BC2VR-…-win64.zip** intact, and run **Install.cmd**.
   First setup needs internet access for portable dependencies.
3. Open the **BC2 VR** desktop shortcut, use **Choose game folder** to select
   `BFBC2Game.exe`, connect your headset and select **Launch BC2 in VR**.
4. Choose your campaign in the VR menu: point with the right controller and select with
   its trigger.

The first launch prepares equipment and audio caches from your installed game. Python is
bundled; the first asset preparation downloads a pinned FFmpeg audio decoder (about 77 MB)
from its upstream GitHub release. No game executable, assets or saves are distributed.

The launcher checks the game executable and the selected OpenXR runtime before starting.
An unverified build is reported with a fingerprint for feedback; that is not blanket
support for every EA, Steam or retail executable. The launcher never changes your OpenXR
runtime or game settings. **Stop VR** ends the mod session and leaves BC2 and your VR
software open.

## Controls

| Action | Input |
| --- | --- |
| Move / snap turn | Left stick / right stick |
| Fire | Right trigger |
| Weapon handling | Grips (supported weapons) |
| Toggle crouch | Click and release the left stick |
| Sprint | Hold Y |
| Recenter | Hold both stick clicks for one second (keeps your crouch posture) |
| Pause menu | Left menu button, or hold X+Y for half a second if the runtime reserves it |

## Updating

Close BC2, then select **Check for updates → Install update** with **Include pre-alpha
hotfixes** enabled. Settings and one previous version are kept; **Roll back** returns to
it. The next launch may prepare the local equipment/audio cache again.

If the launcher reports a damaged package, or an older updater cannot continue: download
the latest Setup, run **Install.cmd** and choose your **existing launcher folder (the one
containing `active.json`)**. It replaces a damaged copy only after the replacement is
verified, and keeps your settings and previous version.

## Troubleshooting

You never need to delete or reinstall BC2 or BC2VR for the problems below.

- **Direct3D 11 check fails:** close BC2, set `DxVersion=11` in
  `Documents/BFBC2/settings.ini`, then retry.
- **Startup seems slow:** keep the headset connected until the game reaches its main
  menu. Startup waits for native VR input before it reports success.
- **VR stopped but BC2 is still open:** select **Restart BC2 before launch**, or close BC2
  normally and launch again. Wait for any cleanup message to finish.
- **Settings cannot be read:** use the offered recovery action; the original file is
  backed up first.
- **"Unverified executable":** support for that exact game build still needs
  verification. Switching headset runtimes does not change this.
- **Steam executable rejected:** enable **Steam compatibility (experimental)** and launch
  normally. It keeps the native interface checks and does not force SteamVR. Gameplay on
  Steam builds, including weapon handling, is not yet verified.
- **"Generated assets must not be written into the game installation":** update to the
  latest version. Installing the launcher directly into the game root or its stock
  `Dist`/`Package` folders is unsupported.
- **Anything else:** use **Report feedback → Save diagnostics for review** and attach the
  ZIP (see below).

The desktop game resolution does not need to be 16:9 for menu pointing.

## What works and what doesn't

Included: native stereo, tracked weapons and support hands, roomscale movement, physical
equipment handling, and manual reloads for supported weapons.

Not finished: death/reload crashes (no accepted fix), vehicles, destruction rendering, the
rest of the campaign after the opening, knife polish, extended play and reconnects,
unsupported weapons, manual LMG reloads and some magnified scopes. Nambu launch/impact
alignment and the recenter correction still need headset checks.

Automated tests cover installer and update layouts and runtime selection; they do not
emulate other GPUs, headset connections or store executables.

## Feedback

Use **Report feedback** in the launcher or
[open an issue](https://github.com/justiceofrip/BC2VR/issues/new/choose). Include your
headset and connection, version, mission, weapon and steps to reproduce. Short videos
with timestamps help with visual or interaction problems.

**Report feedback → Save diagnostics for review** creates a small ZIP from bounded text
logs and build details, then opens its folder (also reachable via **Open logs →
feedback**, file **BC2VR-diagnostics.zip**). Review **Report.txt** before attaching it.
Nothing uploads automatically; game assets, settings, screenshots and memory dumps are
excluded.

This is an unofficial community mod. Framework source and development are in
[FrostbiteVR](https://github.com/justiceofrip/FrostbiteVR).
