Since I already explained how the tiling solutions worked in [Landscape Material Remove Tiling](Landscape-Material-Remove-Tiling.md), I'll just explain briefly which variables I promoted to input parameters and what structural changes I made.

This function enables you to apply tiling fixes on more than one landscape materials without having the need to copy and paste the entire solutions.

- Setting the material function:

  First I created a material function by right clicking on the content browser, and clicking on Material/Advance/Material Function.

  I created 6 function inputs by right click + type function input, 4 of them were Texture2D material textures and 2 of them were scalar UV Far Size and UV Close Size.
  
  I connected my Texture2D input nodes to texture samples and connected the RGBs to the appropriate pins and assigned their UVs.
  
  <img width="853" height="533" alt="Screenshot 2026-07-21 130528" src="https://github.com/user-attachments/assets/3e8add3c-c71c-437c-aaa7-60b209d3e161" />
