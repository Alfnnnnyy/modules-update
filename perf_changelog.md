## Perf v2.5.9 (v259)

### Catatan Perubahan (Changelog):
- **Deteksi Game Instan (Prioritas 1):** Mengganti pembacaan dumpsys ke `dumpsys activity top` sehingga game aktif di layar langsung terdeteksi dalam 30ms tanpa tertutup launcher Home.
- **Kunci 120 FPS / Anti-Drop 90Hz:** Mengunci `is_smart_fps = 0` pada HyperOS untuk mematikan Dynamic Smart FPS yang sering menurunkan refresh rate ke 90Hz saat suhu hangat.
- **Reset 70 Cooling Devices:** Menambahkan reset seluruh cooling device sistem (`display-fps`, `gpu`, `cpu`) ke State 0 saat game berjalan.
- **Pembaruan KernelSU Otomatis:** Integrasi `updateJson` langsung ke mirror publik `modules-update`.

### Varian Modul:
1. `Perf-v2.5.9-NonReplace.zip` (Rekomendasi): 100% tanpa modifikasi partisi system/odm.
2. `Perf-v2.5.9-ReplaceThermal.zip` (Ekstrem): Mengganti config thermal bawaan Xiaomi HyperOS.
