**Tags:** Unreal Engine 5.8, Nanite, Landscape, Ray Traced Shadows, Shadow Artifacts, Rendering, Workaround

---
**Update:** It turned out this was an Unreal Engine 5.8 problem and didn't occur with the same setup in UE 5.7.4
---

After enabling Ray Traced Shadows through the Project Settings, I encountered an issue where blocky shadow artifacts appeared as I moved farther away.

<img width="853" height="533" alt="Screenshot 2026-07-18 233622" src="https://github.com/user-attachments/assets/044ad1ff-653a-418e-88b9-af50f39589bf" />


After days of research and selling my soul to the devil, I finally isolated the problem to the interaction between Ray Traced Shadows and my Nanite-enabled landscape. Disabling either Nanite or Ray Traced Shadows eliminated the artifacts.

Since I wanted my non-landscape objects to continue benefiting from Ray Traced Shadows, I disabled the Cast Ray Traced Shadows option through my landscape material blueprint. This prevented the landscape from participating in the ray-traced shadow pass, and the artifacts disappeared.

<img width="853" height="533" alt="Screenshot 2026-07-18 233733" src="https://github.com/user-attachments/assets/9f77c5c9-7fa0-4671-bff0-222105f3066b" />

## Tested Solutions

Disable Nanite ❌
- Fixes the issue, but disables Nanite.

Disable Ray Traced Shadows ❌
- Fixes the issue, but removes RT shadows globally.

Disable Nanite Tessellation ❌
- No effect and the issue persists.

Change landscape material ❌
- No effect and the issue persists.

Increase `r.RayTracing.NormalBias` ❌
- Hides the artifacts but is not a proper solution.

Set `r.Shadow.DistanceScale` to `0`. ❌
- Landscape shadows appeared correct.
- However, all shadows cast by other objects disappeared.
- Not a viable solution.

Disable `Cast Ray Traced Shadows` in the landscape material. ✅
- Removes the artifacts while allowing other meshes to continue using Ray Traced Shadows.

## Tested in
- Unreal Engine 5.8
- New blank project

## Status
- Workaround
