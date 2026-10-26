# BC2VR 0.1.13 — Launcher diagnostics

This launcher-only pre-alpha update improves the information available when startup fails. Its VR/gameplay binaries are unchanged from 0.1.12.

- Startup distinguishes a confirmed game exit from an unavailable or mismatched process check. It includes the actual exit code when available.
- **Report feedback → Save diagnostics** now includes bounded, sanitized window-activation logs alongside session information. Nothing is uploaded automatically.
- Existing settings and valid asset caches are preserved. The updater keeps 0.1.12 available for rollback.

Install through **Check for updates → Install update**, with **Include pre-alpha hotfixes** enabled. New users can download **BC2VR-Setup-0.1.13.zip**, extract it, and run **Install.cmd**.

Validation: the extracted public package passed 141 offline startup, session and feedback checks, plus fresh-install, update, rollback and settings/cache-preservation checks. Archive comparison verified that only three launcher scripts and version/hash metadata changed. No new headset or campaign acceptance is claimed.

## Current startup reports

The reported Steam executable with fingerprint beginning `22e96001` remains unverified. That is separate from the non-Steam Pimax user's window-activation failure. This release does not claim either underlying problem is fixed; the improved diagnostics should identify the latter more accurately. Please share the reviewed diagnostics ZIP from the new version rather than deleting/reinstalling the game.

## Development update

The rendering work has measured **44.6 → 89.1 fresh stereo pairs per second** at **2784×3024 per eye** in a matched emulated comparison. This compares two development configurations, not 0.1.12 against this release, and it is not yet a physical-headset FPS result.

A real-game checkpoint-reload test now recovers both eye images and controller input. Loading timeouts exposed by that test are still being checked. These rendering/recovery changes are not included in 0.1.13. Destruction artifacts, broader vehicle/death/reconnect coverage, HUD flicker and weapon polish remain in progress.
