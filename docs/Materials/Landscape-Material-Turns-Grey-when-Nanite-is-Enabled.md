**Tags:** Unreal Engine 5.8, Material turns grey, Landscape Layer Blend, Nanite, Engine Bug

I enabled Nanite in my UE 5.8 project because I wanted to use Tessellation and material displacement to give my landscape a 3D look.

But when I tried to use the Landscape Layer Blend node in order to paint my landscape with different materials, the entire material turned grey and it remained that way even after creating and assigning my layers and Layer Info assets.

<img width="853" height="533" alt="Screenshot 2026-07-21 141547" src="https://github.com/user-attachments/assets/fa2ea523-f842-47b0-b3eb-4bf3aaea0d56" />

After a full day of debugging I finally isolated the problem to the interaction between Nanite and the Landscape Layer Blend node.

No matter what I tried, I couldn't get them to work at the same time.

I even tried opening a new project in UE 5.8 but the issue persisted to the point where I started to suspect it was an engine bug in my version.

So I tried the exact setup in UE 5.7.4 and quite frankly, I could use the Landscape Paint tool and Nanite at the same time.

## Made in
- Unreal Engine 5.8
- Blank Project

## Status
- Workaround
