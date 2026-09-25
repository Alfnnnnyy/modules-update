## Perf v2.6.0 (v260)

### Catatan Perubahan (Changelog):
- **Bypass Pembatasan Cas Qualcomm/Xiaomi (Anti-Tekor Game):** Membuka batasan suhu dan restriksi arus pengisian daya (`qcom-battery/remove_temp_limit`, `restrict_cur`, `fastcharge_mode`, `constant_charge_current_max` 9A) saat Game Mode aktif, mengeliminasi masalah baterai turun/tekor saat main game sambil cas.
- **Eliminasi Daemon Stutter / FPS Drop:** Mengubah siklus daemon menjadi *state-transition only* (`applied_mode`). Tidak ada lagi spam fork shell, chmod, dan IPC SurfaceFlinger setiap detik di tengah-tengah gameplay.
- **Auto-Switch Mode Instan:** Memangkas leave grace timer dari 45 detik menjadi 4 detik dan memperbaiki sinkronisasi status. Begitu keluar dari game, sistem langsung otomatis kembali ke mode Balance atau Powersafe tanpa tertahan di Game Mode.
- **Governor Scaling Cerdas (Anti-Overheat):** Mengatur frekuensi dasar CPU game ke 65% clock max dan membiarkan scheduler menggenjot ke 100% secara dinamis, mencegah panas ekstrem (15W-20W) dan *hardware duty-cycle throttling* silikon.
