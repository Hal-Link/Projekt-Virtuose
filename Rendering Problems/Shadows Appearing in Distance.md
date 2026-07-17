After I enabling ray traced shadows I encountered a problem
where weird looking shadows appeared when I moved away from my landscape.
<img width="1280" height="800" alt="Screenshot 2026-07-17 165043" src="https://github.com/user-attachments/assets/01fbe4fc-63f6-4940-baa0-7fa5cecf61c3" />

After some digging I realized that the problem was caused by virtual shadow maps (VSM)
that lowers the quality of shadows the furhter camera is from an object.
<img width="853" height="533" alt="Screenshot 2026-07-17 165205" src="https://github.com/user-attachments/assets/d99bf5a8-746b-4a7c-ab01-be27c52d6e43" />

Finally after changing the shadow map method to shadow maps,
the problem was resolved even though it might cause optimization problems in some systems.
<img width="853" height="533" alt="Screenshot 2026-07-17 165219" src="https://github.com/user-attachments/assets/e131e92b-1cff-4cc2-b7b6-3e90c80aa541" />
