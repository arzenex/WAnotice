# WA Captions

Sirf WhatsApp notifications ko transparent overlay pe white text captions ki tarah dikhata hai, typewriter animation ke saath (letter-by-letter reveal).

## Kaise chalayein
1. Android Studio mein is folder ko "Open" karo (existing project).
2. Gradle sync hone do — dependencies internet se download honge.
3. App ko phone/emulator pe run karo.
4. App kholke dono permissions grant karo:
   - "Display over other apps" (overlay)
   - "Notification access" (WA Captions ko list mein enable karo)
5. Khud ko ek WhatsApp message bhejo (ya kisi se aane do) — caption bottom mein type-hote hue dikhega, phir fade out ho jayega.

## Customize karne ke liye
- `CaptionOverlayService.kt`:
  - `charDelayMs` — typewriter speed (kam value = fast typing)
  - `holdDurationMs` — caption kitni der screen pe ruke poora type hone ke baad
  - `textSize`, `y` (position from bottom) — layout tweak
- `WaNotificationListener.kt`:
  - `waPackages` — agar WhatsApp Business bhi chahiye to already included hai; hata sakte ho agar sirf ek chahiye

## Note
- Ye sirf notification text dikhata hai (jo WhatsApp OS ko bhejta hai) — end-to-end encrypted message content hi hai jo notification mein already visible hota hai, koi extra access nahi le raha.
- Kuch phones (Xiaomi/Oppo/Vivo) mein background/autostart restrictions ki wajah se overlay service kabhi kabhi OS band kar deta hai — agar aisa ho to app ko battery optimization list se hata dena "unrestricted" pe.
