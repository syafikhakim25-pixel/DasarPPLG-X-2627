# 🚀 Syafiq Hakim | Personal GitHub Profile

Halo! Saya **Syafiq Hakim**, siswa kelas X **Rekayasa Perangkat Lunak (RPL)** di **SMK Muhammadiyah 3 Tangerang Selatan**. 

Repositori ini menampilkan animasi pertarungan luar angkasa bergaya retro yang dibuat otomatis dari grafik kontribusi GitHub saya (menggunakan `gh-space-shooter`).

### 🎮 Kontribusi GitHub Saya

<!-- Tautan absolut ke gambar untuk memastikan gambar muncul setelah Action berjalan -->
![Syafiq Hakim GitHub Game](https://raw.githubusercontent.com/syafikhakim-pixel/syafikhakim-pixel/main/game.gif)

---

## 👨‍💻 Tentang Saya
* 🏫 **Sekolah:** SMK Muhammadiyah 3 Tangerang Selatan
* 🎒 **Kelas:** X RPL (Rekayasa Perangkat Lunak)
* 📧 **Email:** [syafikhakim25@gmail.com](mailto:syafikhakim25@gmail.com)
* 🐙 **GitHub:** [@syafikhakim-pixel](https://github.com/syafikhakim-pixel)

---

## 🔧 GitHub Action (Update Otomatis)

Grafik animasi di atas diperbarui secara otomatis setiap hari menggunakan GitHub Action. 

File konfigurasi berada di `.github/workflows/update-game.yml`:

```yaml
name: Update Space Shooter Game

on:
  schedule:
    - cron: '0 0 * * *'  # Berjalan otomatis setiap tengah malam UTC
  workflow_dispatch:     # Bisa dijalankan manual kapan saja

permissions:
  contents: write

jobs:
  update-game:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 2

      - uses: czl9707/gh-space-shooter@v2
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          username: 'syafikhakim-pixel'
          output-path: 'game.gif'
