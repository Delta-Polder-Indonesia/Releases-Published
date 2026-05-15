# 🏆 Bintang Toba Pro - Chess.com Assistant

**Version:** 1.2.0  
**License:** GPL-3.0-only  
**Author:** Delta-Polder-Indonesia  
**Platform:** Chess.com (via Tampermonkey/Violentmonkey)

---

## 📖 Deskripsi

**Bintang Toba Pro** adalah userscript premium untuk Chess.com yang menyediakan berbagai fitur otomatisasi dan analisis catur menggunakan Stockfish engine. Script ini dirancang untuk membantu pemain memahami posisi, melatih kemampuan, dan mengotomatisasi tindakan repetitif.

---

## ⚡ Fitur Utama

### 🧠 Engine Analysis
- **Stockfish 10** integration dengan multi-PV support
- Real-time evaluation (CP & Mate)
- Principal Variation (PV) arrows visualization
- Best move arrows dengan color grading
- Position analysis mode

### 🎯 Auto Move Execution
- Auto-run dengan customizable delay
- Humanized move timing (anti-detection)
- Clock sync mode (adaptive delay based on remaining time)
- Opening book support (external JSON)
- Consensus move selection

### 🔄 Premove System
- Smart premove dengan safety check
- CCT analysis (Checks, Captures, Threats)
- Risk assessment & confidence scoring
- Multi-PV convergence check
- Recapture & forced move detection

### ♟️ Auto Resign
- Mate-based resignation (M1-M10)
- Centipawn-based resignation (-100cp to -5000cp)
- Instant trigger for mate evaluation
- Gradual decay for CP evaluation (anti-false-positive)

### 🎮 Auto Match
- Automatic new game detection
- Auto-click "New Game" button
- Support for Indonesian & English UI
- Auto-run enable after new game (3s delay)
- Rematch decline support

### 📊 Statistics & Tracking
- ACPL (Average Centipawn Loss) tracking
- Move history with grades
- Evaluation bar with delta indicator
- Real-time diagnostics display

### 🛡️ Safety Features
- Blunder guard for analysis mode
- Stability check before auto-play
- Position verification before move execution
- Token system for premove execution
- Error recovery & self-healing workers

---

## 📦 Instalasi

### Prerequisites
1. **Browser:** Chrome, Firefox, Edge, atau browser berbasis Chromium/Gecko
2. **Extension Manager:** Tampermonkey atau Violentmonkey

### Langkah Instalasi

#### Option 1: Dari GreasyFork (Recommended)
```
1. Kunjungi halaman GreasyFork script
2. Klik tombol "Install script"
3. Konfirmasi instalasi di Tampermonkey
4. Script akan aktif otomatis di chess.com
```

#### Option 2: Manual Installation
```
1. Download file engine.js
2. Buka Tampermonkey dashboard
3. Klik "Create a new script"
4. Copy-paste seluruh konten engine.js
5. Save (Ctrl+S)
6. Enable script
```

#### Option 3: Dari GitHub
```bash
# Clone repository
git clone https://github.com/Delta-Polder-Indonesia/Egine-chess-tempermonkey-pro.git

# Atau download langsung
wget https://raw.githubusercontent.com/Delta-Polder-Indonesia/Egine-chess-tempermonkey-pro/refs/heads/main/engine.js
```

---

## ⚙️ Konfigurasi

### Panel Settings

| Setting | Default | Range | Deskripsi |
|---------|---------|-------|-----------|
| **Min Delay** | 0.5s | 0.05-60s | Delay minimum untuk auto move |
| **Max Delay** | 3.0s | 0.05-60s | Delay maksimum untuk auto move |
| **Custom Depth** | 15 | 1-30 | Engine analysis depth |
| **Skill Level** | 20 | 0-20 | Stockfish skill level |
| **ELO Rating** | 1600 | 300-3200 | Human mode ELO |
| **Auto Resign (Mate)** | M3 | M1-M10 | Batas resign untuk mate |
| **Auto Resign (CP)** | -1000 | -100 to -5000 | Batas resign untuk centipawn |
| **Clock Sync** | OFF | ON/OFF | Adaptive delay based on clock |
| **Premove** | OFF | ON/OFF | Enable smart premove system |

### Hotkeys

| Shortcut | Action |
|----------|--------|
| `Alt + A..Z` | Set engine depth (1-26) |
| `Ctrl + Shift + H` | Toggle Panic Mode (hide all) |
| `Ctrl + Shift + S` | Toggle Stream Proof Mode |
| `Ctrl + Shift + M` | Toggle Move Execution Mode (Click/Drag) |
| `Ctrl + Shift + ?` | Open Hotkeys Help |
| `Esc` | Toggle panel open/closed |

---

## 🎮 Cara Penggunaan

### Mode Normal (Auto Run)
```
1. Enable "Auto Run" di panel
2. Set delay sesuai preferensi (rekomendasi: 1-3s)
3. Script akan otomatis menganalisis posisi
4. Move akan dieksekusi setelah delay
```

### Mode Analysis
```
1. Enable "Analysis Mode" di panel
2. Pilih warna auto-play (White/Black/Off)
3. Script akan menganalisis terus menerus
4. Auto-play move saat stability threshold tercapai
```

### Mode Premove
```
1. Enable "Premove System" di panel
2. Pilih mode: Every/Capture/Filtered
3. Set confidence threshold (rekomendasi: 60-80%)
4. Script akan premove saat confidence tinggi
```

### Auto Resign Setup
```
1. Enable "Auto Resign" di panel
2. Pilih mode: Mate in atau Centipawn
3. Set threshold:
   - Mate: M3 (resign di M3, M2, M1)
   - CP: -1000 (resign di -1000cp atau lebih buruk)
4. Script akan resign otomatis saat threshold tercapai
```

---

## 🔧 Troubleshooting

### Script Tidak Jalan
```
✅ Pastikan Tampermonkey/Violentmonkey terinstall
✅ Pastikan script enabled di dashboard
✅ Pastikan URL match: https://www.chess.com/*
✅ Refresh halaman chess.com (Ctrl+F5)
✅ Cek browser console untuk error (F12)
```

### Engine Tidak Analisis
```
✅ Cek "Engine Status LED" di panel (harus hijau)
✅ Klik tombol "Reload" di tab More
✅ Pastikan tidak ada script conflict
✅ Clear browser cache
```

### Auto Move Tidak Eksekusi
```
✅ Pastikan "Auto Move Piece" enabled
✅ Cek apakah giliran Anda (LED biru)
✅ Pastikan delay tidak terlalu panjang
✅ Cek console untuk error message
```

### Premove Tidak Jalan
```
✅ Enable "Premove System"
✅ Pastikan bukan giliran Anda
✅ Cek confidence threshold (turunkan jika perlu)
✅ Lihat premove stats di panel
```

### Auto Resign Tidak Trigger
```
✅ Pastikan "Auto Resign" enabled
✅ Cek threshold setting (M4 vs M3)
✅ Untuk CP: butuh 3x trigger berturut-turut
✅ Untuk Mate: instant trigger saat threshold tercapai
```

---

## 🤝 Kontribusi

### Cara Berkontribusi
```
1. Fork repository
2. Buat feature branch (git checkout -b feature/AmazingFeature)
3. Commit perubahan (git commit -m 'Add AmazingFeature')
4. Push ke branch (git push origin feature/AmazingFeature)
5. Open Pull Request
```

### Bug Report
Jika menemukan bug, silakan buat issue dengan format:
```
**Describe the bug**
Deskripsi jelas tentang bug

**To Reproduce**
Langkah untuk reproduce:
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected behavior**
Apa yang seharusnya terjadi

**Screenshots**
Jika ada, tambahkan screenshot

**Environment:**
- Browser: [Chrome/Firefox/Edge]
- Tampermonkey Version: [x.x.x]
- Script Version: [1.2.0]
```

### Feature Request
```
**Is your feature request related to a problem?**
Deskripsi masalah

**Describe the solution you'd like**
Solusi yang diinginkan

**Describe alternatives you've considered**
Alternatif yang sudah dipertimbangkan

**Additional context**
Konteks tambahan
```

---

## 📄 License

Distributed under the **GPL-3.0-only License**.  
See [LICENSE](LICENSE) for more information.

### Commercial Use
❌ **Dilarang** untuk penggunaan komersial tanpa izin  
✅ **Boleh** untuk penggunaan pribadi  
✅ **Boleh** untuk modifikasi dan distribusi (dengan atribusi)

---

## 🙏 Credits

- **Stockfish Team** - Chess engine
- **Chess.com** - Platform (unofficial script)
- **Tampermonkey** - Userscript manager
- **Contributors** - Semua yang berkontribusi

---

## 📞 Support

| Channel | Link |
|---------|------|
| **GitHub Issues** | [Report Bug / Request Feature](https://github.com/Delta-Polder-Indonesia/Egine-chess-tempermonkey-pro/issues) |
| **GreasyFork** | [Script Discussion](https://greasyfork.org/scripts/xxxxxx) |
| **Email** | delta-polder-indonesia@example.com |

---

## ⚠️ Disclaimer

> **PENTING:** Script ini adalah tools untuk **belajar dan latihan catur**.  
> Penggunaan untuk cheating dalam turnamen atau rated games **dilarang keras** dan dapat mengakibatkan:
> - Account ban dari Chess.com
> - Diskualifikasi dari turnamen
> - Rating reset

**Gunakan dengan bijak dan bertanggung jawab!**

---

## 📝 Changelog

### v1.2.0 (Current)
- ✅ Fixed engine lock issue (_goLock immediate release)
- ✅ Opening book cache cleared on new game
- ✅ Timeout IDs auto-trimmed (memory optimization)
- ✅ Auto-resign instant trigger for mate evaluation
- ✅ Auto-match enable auto-run after new game
- ✅ Removed dead code & orphan variables
- ✅ Fixed AutoMatch button priority
- ✅ Fixed AutoMatch anti-"Tanding Ulang" filter

### v1.0.0 (Initial)
- Initial release

---

## 📊 Statistics

| Metric | Value |
|--------|-------|
| **Lines of Code** | ~10,577 |
| **Sections** | 43 |
| **Functions** | ~200+ |
| **Cache Systems** | 3 (CCT, Threat, Syzygy) |
| **Workers** | 3 (Main, Analysis, Premove) |
| **Supported Languages** | ID, EN |

---

**Made with ❤️ by Delta-Polder-Indonesia**
