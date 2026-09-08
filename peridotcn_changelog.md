## PeridotCN-Spoofer v6.3.4 (v16)

### Catatan Perubahan (Changelog):
- **Sinkronisasi Security Patch September 2026:** Memperbarui `ro.build.version.security_patch` dan `ro.vendor.build.security_patch` ke `2026-09-01` (`202609`) agar cocok 100% dengan TEE Hardware Attestation bulan September.
- **Sinkronisasi Hostname Linux Kernel:** Menghubungkan syscall `hostname` dengan `net.hostname` untuk menghilangkan mismatch `gethostname(2)` / `uname -n` (`localhost` vs `android-xxxx`).
- **Auto-Sync Bulanan:** Menambahkan penyesuaian otomatis level patch berbasis bulan berjalan di `service.sh`.
