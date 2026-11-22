# Hospot ACS — WebView APK (Tahap 1)

APK pembungkus dashboard web GenieACS, di-build otomatis oleh GitHub Actions.

## Cara dapat APK-nya (sekali setup)

1. Buat repo kosong di GitHub, misal `hospot-acs` (boleh private).
2. Upload semua isi folder ini ke repo (lihat perintah di bawah), branch `main`.
3. Buka tab **Actions** di repo → workflow **Build APK** jalan otomatis.
4. Setelah hijau (± 2–4 menit), buka run-nya → bagian **Artifacts** → unduh
   `HospotACS-debug-apk` → di dalamnya ada `app-debug.apk`.
5. Kirim `app-debug.apk` ke HP, install (izinkan "install dari sumber tak dikenal").

## Push pertama (dari folder ini)

```
git init
git add .
git commit -m "Tahap 1: WebView APK + workflow"
git branch -M main
git remote add origin https://github.com/USERNAME/hospot-acs.git
git push -u origin main
```

## Mau ganti apa

- **Alamat dashboard** → `app/src/main/java/id/my/hospot/acs/MainActivity.kt`,
  ubah `SERVER_URL`. Harus halaman web (mis. dashboard :8080), BUKAN NBI :7557.
- **Nama app** → `app/src/main/res/values/strings.xml`, ubah `app_name`.
- **ID aplikasi** (`id.my.hospot.acs`) → `app/build.gradle` + `settings`/manifest
  namespace. Biarin dulu kalau belum perlu.
