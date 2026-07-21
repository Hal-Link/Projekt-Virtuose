**Tags:** Unreal Engine 5.8, Material turns grey, Landscape Layer Blend, Nanite, Engine Bug

I enabled nanite in UE 5.8 my project because I wanted to use Tessellation and material displacement to give my landscape a 3D look.

But when I tried to use Landscape Layer Blend node in order to paint my landscape with different materials, the entire material turned grey and it remained that way even after assigning my layers and layer infos.

<img width="853" height="533" alt="Screenshot 2026-07-21 141547" src="https://github.com/user-attachments/assets/fa2ea523-f842-47b0-b3eb-4bf3aaea0d56" />

After a full day of debugging I finally isolated the problem into the relationship between nanite and Landscape Layer Blend.

No matter what I tried, I couldn't get them to work at the same time, I tried opening a new project and it kept happening until the point I started to think it was an engine bug in UE 5.8.

So I tried it on UE 5.7.4 and quite frankly, I could Landscape Paint.

## Made in
- Unreal Engine 5.8
- Blank Project

## Status
- Workaroun
