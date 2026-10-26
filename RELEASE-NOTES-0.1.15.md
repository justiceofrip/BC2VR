BC2VR 0.1.15 adds **Steam compatibility (experimental)** and fixes a launcher error that could leave a supported game running only on the monitor.

The process-verification fix addresses a reported startup race: Windows had not yet provided the executable path through the launcher's initial lookup, so it saved an empty path and later rejected the live game. The launcher now obtains a missing path from the original Windows process handle and verifies the same process identity.

For the Steam tester whose executable was rejected: enable **Steam compatibility (experimental)** in the launcher, then launch normally. The setting is saved. This option targets the reported Steam executable and retains the native adapter's interface checks. Its actual Steam gameplay has not been tested here; some weapon-handling features still require separate verification for that executable. It is a compatibility test, not a claim that every Steam build is supported.

Close BC2 before updating, choose **Check for updates → Install update**, then close and reopen the launcher. Keep **Include pre-alpha hotfixes** enabled. New installs can use **BC2VR-Setup-0.1.15.zip** and **Install.cmd**. Settings and the previous package are preserved. The next launch may prepare its local equipment/audio cache again under the updated recipe.

The 0.1.14 diagnostics-button fix remains included. If startup fails, use **Report feedback → Save diagnostics for review** and attach the reviewed **BC2VR-diagnostics.zip** from the folder that opens.

This is a launcher hotfix. The VR/gameplay binaries remain unchanged. Offline checks cover settings persistence, candidate rejection/admission, menu startup and session option propagation. Process-identity checks use a real hidden 32-bit process without launching BC2 or taking desktop input.
