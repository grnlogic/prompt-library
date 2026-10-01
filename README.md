<div align="center">

# 📚 Prompt Library

### Koleksi prompt siap pakai — tinggal isi variabel, langsung tempel ke AI.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/grnlogic/prompt-library)](https://github.com/grnlogic/prompt-library/commits/main)
[![Repo Size](https://img.shields.io/github/repo-size/grnlogic/prompt-library)](https://github.com/grnlogic/prompt-library)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)

</div>

---

## 🤔 Kenapa Repo Ini?

Sering copy-paste prompt yang sama berulang kali? Atau kesulitan merumuskan prompt yang tepat untuk tugas tertentu?

Repo ini menyimpan koleksi prompt yang sudah **teruji, terstruktur, dan siap pakai** — lengkap dengan variabel `{{...}}` yang tinggal kamu ganti sesuai konteks. Tidak perlu pusing menyusun prompt dari nol.

---

## 📋 Daftar Isi

- [Kategori Prompt](#kategori-prompt)
- [Struktur Folder](#struktur-folder)
- [Cara Pakai](#cara-pakai)
- [Contoh Cepat](#contoh-cepat)
- [Cara Berkontribusi](#cara-berkontribusi)
- [Lisensi](#lisensi)

---

## 🗂️ Kategori Prompt

| Kategori | Deskripsi | Jumlah Prompt | Link |
|----------|-----------|:---:|------|
| 🎓 **Akademik** | Penulisan ilmiah, laporan, presentasi | 1+ | [→ akademik/](./akademik/) |
| 💻 **Coding** | Debugging, refactor, code review, dokumentasi | 2+ | [→ coding/](./coding/) |
| 🤖 **Agents** | System prompt, workflow, template AGENTS.md | 2+ | [→ agents/](./agents/) |

---

## 📁 Struktur Folder

```
prompt-library/
├── 📄 AGENTS.md              ← Panduan untuk AI agent
├── 📄 README.md              ← Kamu sedang baca ini
├── 📄 LICENSE                ← MIT License
├── 📄 CONTRIBUTING.md        ← Cara berkontribusi
├── 📄 CHANGELOG.md           ← Riwayat perubahan
│
├── 🎓 akademik/
│   ├── penulisan-ilmiah/     ← Abstrak, makalah, esai
│   ├── laporan/              ← Laporan PKL, penelitian
│   └── presentasi/           ← Narasi slide, public speaking
│
├── 💻 coding/
│   ├── debugging/            ← Analisis error & stack trace
│   ├── refactor/             ← Perbaikan kualitas kode
│   ├── code-review/          ← Review PR & kode
│   └── dokumentasi/          ← Docstring, README otomatis
│
├── 🤖 agents/
│   ├── system-prompts/       ← System prompt siap pakai
│   ├── workflows/            ← Alur kerja multi-langkah
│   └── agents-md-templates/  ← Template AGENTS.md
│
├── 📐 templates/
│   └── prompt-template.md    ← Template standar prompt baru
│
└── 📖 docs/
    ├── prompt-engineering-tips.md
    └── naming-conventions.md
```

---

## 🚀 Cara Pakai

Sangat mudah — tiga langkah:

**1. Temukan prompt yang sesuai**
Jelajahi folder kategori atau gunakan search GitHub (`/` untuk fokus ke search bar).

**2. Salin prompt**
Buka file `.md`, salin teks di dalam code block `💬 Prompt`.

**3. Isi variabel dan tempel ke AI**
Ganti semua `{{variabel}}` dengan nilai yang sesuai, lalu tempel ke ChatGPT, Claude, Gemini, atau AI favoritmu.

```
# Sebelum: ada {{variabel}}
Analisis error berikut di {{bahasa_pemrograman}}: ...

# Sesudah: variabel sudah diisi
Analisis error berikut di Python 3.11: ...
```

---

## ⚡ Contoh Cepat

Mau rapikan abstrak jurnal? Buka [`akademik/penulisan-ilmiah/rapikan-abstrak-jurnal.md`](./akademik/penulisan-ilmiah/rapikan-abstrak-jurnal.md), salin promptnya, lalu:

```
Kamu adalah editor jurnal ilmiah berpengalaman di bidang kecerdasan buatan.

Berikut adalah abstrak yang perlu kamu perbaiki:
---
[paste abstrakmu di sini]
---

Tugasmu:
1. Pastikan abstrak mencakup: latar belakang, tujuan, metode, temuan
2. Buang kalimat basa-basi
3. Batas maksimal: 200 kata
4. Gunakan bahasa Indonesia formal
...
```

Hasilnya? Abstrak yang rapi, padat, dan siap submit — dalam hitungan detik.

---

## 🤝 Cara Berkontribusi

Ada prompt bagus yang ingin dibagikan? Lihat panduan lengkapnya di [`CONTRIBUTING.md`](./CONTRIBUTING.md).

Singkatnya:
1. Fork repo ini
2. Salin `templates/prompt-template.md` ke folder yang sesuai
3. Isi semua bagian template
4. Buat Pull Request

---

## 📜 Lisensi

Repo ini dilisensikan di bawah [MIT License](./LICENSE) — bebas dipakai, dimodifikasi, dan didistribusikan dengan menyertakan atribusi.

---

<div align="center">

Dibuat dengan ☕ oleh **[Fajar Geran Arifin](https://github.com/grnlogic)**

⭐ Kalau repo ini membantu, jangan lupa kasih star!

</div>