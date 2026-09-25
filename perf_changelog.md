## Perf v2.6.1 (v261)

### Catatan Perubahan (Changelog):
- **Deteksi Game Window Mengambang / Sidebar:** Menambahkan pembacaan langsung dari Linux kernel `top-app` cgroup (`/dev/cpuset/top-app/cgroup.procs`) sehingga game yang berjalan di layar utama tetap terdeteksi 100% aktif meskipun ada jendela mengambang (floating window WebUI / Game Turbo sidebar) di atasnya.
- **Fix Mount Gate Varian NonReplace:** Memperbaiki bug di mana engine daemon langsung mati/disabled saat menggunakan varian NonReplace karena mencari folder overlay yang memang sengaja ditiadakan.
- **Fix Dynamic Governor GKI 6.1 (Anti-100°C):** Mengganti penulisan governor `walt` menjadi `schedutil` (governor dinamis standar Android GKI 6.1). Pada mode Balance, clock CPU langsung turun ke 400 MHz saat idle, mengembalikan suhu dari 100.7°C ke 40°C.
- **Bypass Pembatasan Cas Qualcomm/Xiaomi (Anti-Tekor Game):** Membuka batasan suhu dan restriksi arus pengisian daya (`qcom-battery/remove_temp_limit`, `restrict_cur`, `fastcharge_mode`, `constant_charge_current_max` 9A) saat Game Mode aktif, mengeliminasi masalah baterai turun/tekor saat main game sambil cas.
- **Eliminasi Daemon Stutter / FPS Drop:** Mengubah siklus daemon menjadi *state-transition only* (`applied_mode`). Tidak ada lagi spam fork shell, chmod, dan IPC SurfaceFlinger setiap detik di tengah-tengah gameplay.
- **Auto-Switch Mode Instan:** Memangkas leave grace timer dari 45 detik menjadi 4 detik dan memperbaiki sinkronisasi status.
