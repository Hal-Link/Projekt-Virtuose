**Tags:** Unreal Engine 5.7, Materials, Tiling, Distance Tiling, Color Variation, Material Function

Since I already explained how the tiling solutions worked in [Landscape Material Remove Tiling](Landscape-Material-Remove-Tiling.md), I'll just explain briefly which variables I promoted to input parameters and what structural changes I made.

This function enables you to apply tiling fixes on more than one landscape materials without having the need to copy and paste the entire solutions.

- Setting the material function:

  First I created a material function by right clicking on the content browser, and clicking on Material/Advance/Material Function.

  I created 6 function inputs by right click + type function input, 4 of them were Texture2D material textures and 2 of them were scalar UV Far Size and UV Close Size.
  
  I connected my Texture2D input nodes to texture samples and connected the RGBs to the appropriate pins and assigned their UVs.
  
  <img width="853" height="533" alt="Screenshot 2026-07-21 130528" src="https://github.com/user-attachments/assets/3e8add3c-c71c-437c-aaa7-60b209d3e161" />

---

This part is where I changed a few things:

In my solution explanation, I was first implementing Distance Tiling fix and then Color Variation but then I couldn't change the UV size of my Color Variation Noise which made the color variation appear the same everywhere so I decided to switch the order to have 2 Color Variation structures, UVs of which I can set separately.

---

  I created a GetMaterialAttributes node and implemented Color Variation as shown in the pictures.

  In this proccess, I used 3 more function inputs for both Far View and Close View to replace: Tint Color, Noise Texture and Noise Texture UV Size.

  Then I copied the structure and by giving appropriate names and plugged our base MakeMaterialAttribute nodes to them.

  <img width="853" height="533" alt="Screenshot 2026-07-21 133352" src="https://github.com/user-attachments/assets/5f6f18e9-e01b-44b7-a2f9-34557b5e51a7" />

  <img width="853" height="533" alt="Screenshot 2026-07-21 133510" src="https://github.com/user-attachments/assets/042aff85-cbdc-4bea-84d7-a7259c80658d" />

  Finally by using the 2 output pins of the implemented Color Variation, I implemented Distance Tiling and plugged them all into function output result node, giving you a     function you can fully customize with 14 input pins.

  <img width="853" height="533" alt="Screenshot 2026-07-21 132142" src="https://github.com/user-attachments/assets/4ae4ef69-0ce7-414f-9570-c29e5c8e1144" />

## Made in
- Unreal Engine 5.7.4
- New Project

## Status
- Material Function
