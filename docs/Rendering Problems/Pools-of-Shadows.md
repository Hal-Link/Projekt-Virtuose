I encountered a problem with ray traced shadows, little pools of shadows on nanite tessellation enabled landscape.

<img width="853" height="533" alt="Screenshot 2026-07-17 170950" src="https://github.com/user-attachments/assets/4e1156f2-0114-496e-81f8-d87ad59478ab" />

I eventually found two solutions, one being the same as the solution of [Shadows Appearing in Distance](Shadows-Appearing-in-Distance.md), but again, this solution might cause optimization problems in lower spec systems.

The other solution is to increase r.RayTracing.NormalBias to a value about 5, the default being 0.1.

<img width="853" height="533" alt="Screenshot 2026-07-17 172610" src="https://github.com/user-attachments/assets/1cd89977-8828-4daa-a030-8eb649c12978" />

This solves the problem by elevating ray origins of the objects, ignoring the light blockages that are too close to the ground and prevent self-shadowing.
