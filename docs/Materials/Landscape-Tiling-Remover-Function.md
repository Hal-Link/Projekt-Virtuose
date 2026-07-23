**Tags:** Unreal Engine 5.7, Materials, Tiling, Distance Tiling, Color Variation, Material Function

Since I already explained how the tiling solutions worked in [Landscape Material Remove Tiling](Landscape-Material-Remove-Tiling.md), I'll just explain briefly which variables I promoted to input parameters and what structural changes I made.

This function enables you to apply tiling fixes on more than one landscape material without needing to copy and paste the entire solutions.

- Setting the material function:

  First I created a material function by right-clicking in the Content Browser, and clicking on Material/Advanced/Material Function.

  I created 6 function inputs by right click + type function input, four of them were Texture2D inputs, and two were scalar inputs: UV Far Size and UV Close Size.
  
  I connected my Texture2D input nodes to texture samples and connected their RGBs to the appropriate pins and assigned their UVs.
  
  <img width="853" height="533" alt="Screenshot 2026-07-21 130528" src="https://github.com/user-attachments/assets/3e8add3c-c71c-437c-aaa7-60b209d3e161" />

---

This part is where I changed a few things:

In my solution explanation, I was first implementing the Distance Tiling fix and then the Color Variation but then I couldn't change the UV size of my Color Variation Noise textyre which made the color variation appear the same everywhere so I decided to switch the order to have two Color Variation structures whose UVs of I can set separately.

---

  I created a GetMaterialAttributes node and implemented Color Variation as shown in the pictures.

  In this process, I used 3 more function inputs for both the Far View and Close View to replace: Tint Color, Noise Texture and Noise Texture UV Size.

  Then I copied the structure, gave them appropriate names and plugged the base MakeMaterialAttribute nodes into them.

  <img width="853" height="533" alt="Screenshot 2026-07-21 133352" src="https://github.com/user-attachments/assets/5f6f18e9-e01b-44b7-a2f9-34557b5e51a7" />

  <img width="853" height="533" alt="Screenshot 2026-07-21 133510" src="https://github.com/user-attachments/assets/042aff85-cbdc-4bea-84d7-a7259c80658d" />

  Finally by using the two output pins of the implemented Color Variation, I implemented Distance Tiling and plugged them into the function output result node, giving you a     function you can fully customize with 14 input pins.

  <img width="853" height="533" alt="Screenshot 2026-07-21 132142" src="https://github.com/user-attachments/assets/4ae4ef69-0ce7-414f-9570-c29e5c8e1144" />

For referance, this is what my function looks like inside my landscape material blueprint, along with the values I tweaked and settled on (You have to use Texture Objects instead of texture samples when plugging into Texture2D inputs):

<img width="853" height="533" alt="Screenshot 2026-07-21 145049" src="https://github.com/user-attachments/assets/b421e24f-2530-45b1-ad31-4d4e4e1bcc94" />

---

**Update:**

I later multiplied the height values of the function by 2 different inputs so that I could apply different magnitudes of tessellation to different materials in my landscape.

<img width="347" height="134" alt="Screenshot 2026-07-23 184414" src="https://github.com/user-attachments/assets/7d81ac0c-4b53-4ad3-a7e5-6bc1cdc78df9" />

<img width="347" height="142" alt="Screenshot 2026-07-23 185101" src="https://github.com/user-attachments/assets/0216fbec-e634-4280-a49e-15f60f4bf51a" />

---

## Made in
- Unreal Engine 5.7.4
- New Project

## Status
- Material Function
