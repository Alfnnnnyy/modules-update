## PeridotCN-Spoofer v6.3.3 (v15)

### 🛡️ Security & Kernel Parity
- **Security Patch Parity:** Added `ro.build.version.security_patch=2026-08-01`, `ro.vendor.build.security_patch=2026-08-01`, `ro.keymaster.xxx.security_patch=2026-08-01`, and `ro.bootimage.build.security_patch=2026-08-01` in both `props.conf` and `seal.conf` to achieve 100% parity with TEE KeyStore Hardware Attestation certificates.
- **Kernel Hostname Synchronization:** Automatically write generated hostname (`android-$SERIAL`) to Linux kernel sysctl `/proc/sys/kernel/hostname` during early boot (`post-fs-data.sh`) and late boot (`service.sh`), resolving `gethostname(2)` and `uname -n` mismatch vs `net.hostname` reported by VDInfos.
- **KernelSU Online Module Update:** Integrated `updateJson` pointing to `Alfnnnnyy/modules-update` public mirror to enable seamless in-app module update notifications and one-tap upgrades in KernelSU / ReSukiSU / APatch / Magisk managers.
