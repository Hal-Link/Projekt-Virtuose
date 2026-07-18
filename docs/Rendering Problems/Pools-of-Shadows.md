**Tags:** Unreal Engine 5.8, Nanite, Landscape, Ray Traced Shadows, Shadow Pools, Rendering, Workaround

I stumbled upon a problem when experimenting with Ray Traced Shadows and a landscape which had a tessellation-enabled and displaced texture on.

<img width="853" height="533" alt="Screenshot 2026-07-17 170950" src="https://github.com/user-attachments/assets/4e1156f2-0114-496e-81f8-d87ad59478ab" />

I eventually found two solutions, one being the same as the solution of [Shadows Appearing in Distance](Shadows-Appearing-in-Distance.md).

The other solution is to increase r.RayTracing.NormalBias to a value about 5 in Console Command, the default being 0.1.

<img width="853" height="533" alt="Screenshot 2026-07-17 172610" src="https://github.com/user-attachments/assets/1cd89977-8828-4daa-a030-8eb649c12978" />

This solves the problem by elevating ray origins of the objects, ignoring the light blockages that are too close to the ground and preventing self-shadowing.

## Tested in
- Unreal Engine 5.8
- New blank project

## Status
- Workaround
