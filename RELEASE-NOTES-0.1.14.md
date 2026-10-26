BC2VR 0.1.14 fixes the **Save diagnostics for review** button. A callback could close the feedback dialog without starting the export, leaving the previous launch error on screen and producing no ZIP.

After updating, close and reopen the launcher. Select **Report feedback → Save diagnostics for review**. Explorer opens the folder containing **BC2VR-diagnostics.zip**. You can also reach it through **Open logs → feedback**. Review Report.txt before sharing; nothing uploads automatically.

This launcher-only hotfix keeps the VR/gameplay binaries, executable checks and asset-cache recipe identical to 0.1.13. It fixes diagnostic collection; it does not claim to fix the reported native-input startup timeout or the separate unverified Steam executable.

Validation covers the actual dialog click wiring (including the old failure and cancellation), diagnostic ZIP generation through the real worker, and isolated fresh-install/update/rollback. No game or headset test was needed for this UI change.

Existing users: keep **Include pre-alpha hotfixes** enabled, choose **Check for updates → Install update**, then reopen the launcher. Close BC2 before updating. Settings and valid prepared assets are preserved; 0.1.13 remains available for rollback when updating from it.

New installs: download **BC2VR-Setup-0.1.14.zip**, extract it, and run **Install.cmd**. Keep the inner runtime ZIP intact.
