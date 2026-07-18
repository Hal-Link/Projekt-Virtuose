After I enabling ray traced shadows I encountered a problem where blocky looking shadows appeared when I moved away from my landscape.

<img width="853" height="533" alt="Screenshot 2026-07-18 233622" src="https://github.com/user-attachments/assets/044ad1ff-653a-418e-88b9-af50f39589bf" />

After days of digging I realized that the problem was caused by Ray Traced Shadows. Specifically, Ray Traced Shadows were bugging when came into contact with nanite landscapes and possibly other nanite objects though I'm not sure about them.

Since I wanted my non-nanite objects to actually benefit from Ray Traced Shadows, I disabled Cast Ray Traced Shadows option from my landscape material and the shadows disappeared.

<img width="853" height="533" alt="Screenshot 2026-07-18 233733" src="https://github.com/user-attachments/assets/9f77c5c9-7fa0-4671-bff0-222105f3066b" />




