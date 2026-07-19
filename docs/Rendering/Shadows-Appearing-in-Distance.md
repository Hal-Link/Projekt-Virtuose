<<<<<<< HEAD
After I enabling ray traced shadows I encountered a problem where weird looking shadows appeared when I moved away from my landscape.
=======
**Tags:** Unreal Engine 5.8, Nanite, Landscape, Ray Traced Shadows, Shadow Artifacts, Rendering, Workaround
>>>>>>> 0e7077601b26d7c577cc9110ea00e9f7e137a9ee

<<<<<<< HEAD
<img width="1280" height="800" alt="Screenshot 2026-07-17 165043" src="https://github.com/user-attachments/assets/01fbe4fc-63f6-4940-baa0-7fa5cecf61c3" />

After some digging I realized that the problem was caused by virtual shadow maps (VSM) that lowers the quality of shadows the furhter camera is from an object.

<img width="853" height="533" alt="Screenshot 2026-07-17 165205" src="https://github.com/user-attachments/assets/d99bf5a8-746b-4a7c-ab01-be27c52d6e43" />

Finally after changing the shadow map method to shadow maps, the problem was resolved even though it might cause optimization problems in some systems.

<img width="853" height="533" alt="Screenshot 2026-07-17 165219" src="https://github.com/user-attachments/assets/e131e92b-1cff-4cc2-b7b6-3e90c80aa541" />

=======
After enabling Ray Traced Shadows through the Project Settings, I encountered an issue where blocky shadow artifacts appeared as I moved farther away.

<img width="853" height="533" alt="Screenshot 2026-07-18 233622" src="https://github.com/user-attachments/assets/044ad1ff-653a-418e-88b9-af50f39589bf" />


After days of research and selling my soul to the devil, I finally isolated the problem to the interaction between Ray Traced Shadows and my Nanite-enabled landscape. Disabling either Nanite or Ray Traced Shadows eliminated the artifacts.

Since I wanted my non-landscape objects to continue benefiting from Ray Traced Shadows, I disabled the Cast Ray Traced Shadows option in my landscape material. This prevented the landscape from participating in the ray-traced shadow pass, and the artifacts disappeared.

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

>>>>>>> 0e7077601b26d7c577cc9110ea00e9f7e137a9ee