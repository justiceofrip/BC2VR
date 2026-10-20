# BC2VR 0.1.11 — launcher cache-folder hotfix

This update fixes asset preparation failing with “Generated assets must not be written into the game installation” when a dedicated `BC2VR-Launcher` folder is inside the game installation. Generated files stay in that launcher's managed cache. The game root itself and stock `Dist`/`Package` folders remain unsupported launcher destinations.

The native binaries and gameplay payload remain exactly those of 0.1.10. Only the launcher cache-path fix and required package metadata change. All 21 focused cache-path checks and 16 fresh-install, update and rollback checks passed.

Close BC2 and use **Check for updates → Install update**, or download **BC2VR-Setup-0.1.11.zip**, run **Install.cmd**, and choose the existing launcher folder containing `active.json`. Keep **Include pre-alpha hotfixes** enabled. Settings and one previous package are retained for rollback. A new local asset cache may be prepared on the next launch. **No game reinstall is needed.**

Knife interaction has failed current headset testing. Opening-guard/campaign progression and death/reload recovery have not passed acceptance; reported crashes remain unresolved. This release contains no new gameplay fix or headset-acceptance claim.
