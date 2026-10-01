---
judul: "Template AGENTS.md Generik untuk Project Baru"
kategori: agents
tags: [agents-md, template, project-setup, ai-agent, dokumentasi]
model: GPT-4, Claude 3.5 Sonnet, Gemini 1.5 Pro
versi: 1.0
tanggal_update: 2026-10-01
---

# Template AGENTS.md Generik untuk Project Baru

## 🎯 Tujuan

Memberikan template `AGENTS.md` yang siap pakai untuk project baru — mendefinisikan aturan kerja, struktur project, konvensi, dan panduan untuk AI agent agar bisa bekerja secara konsisten dan aman di repo manapun.

---

## 📌 Kapan Dipakai

- Saat memulai project baru dan ingin langsung ada panduan untuk AI agent
- Saat onboarding AI agent ke project yang sudah ada tapi belum punya `AGENTS.md`
- Saat ingin menstandardisasi cara AI agent bekerja di seluruh project tim

---

## 🔧 Variabel yang Harus Diisi

| Variabel | Deskripsi | Contoh Isian |
|----------|-----------|--------------|
| `{{nama_proyek}}` | Nama project | "inventory-system" |
| `{{deskripsi_singkat}}` | Deskripsi 1-2 kalimat | "Sistem manajemen stok berbasis web" |
| `{{bahasa_utama}}` | Stack teknologi | "TypeScript, React, PostgreSQL" |
| `{{branch_utama}}` | Branch utama | "main" |
| `{{owner}}` | Nama + GitHub handle pemilik | "Fajar Geran Arifin (@grnlogic)" |
| `{{struktur_folder}}` | Tree struktur folder | (paste output `tree -L 2`) |
| `{{perintah_dev}}` | Command untuk jalankan dev server | "npm run dev" |
| `{{perintah_test}}` | Command untuk run test | "npm test" |

---

## 💬 Prompt

```
Buatkan file AGENTS.md untuk project {{nama_proyek}} dengan informasi berikut:

**Deskripsi project:** {{deskripsi_singkat}}
**Stack teknologi:** {{bahasa_utama}}
**Branch utama:** {{branch_utama}}
**Pemilik:** {{owner}}

**Struktur folder:**
```
{{struktur_folder}}
```

**Command penting:**
- Dev: `{{perintah_dev}}`
- Test: `{{perintah_test}}`

AGENTS.md harus mencakup bagian-bagian berikut:

1. **Ringkasan Project** — nama, deskripsi, stack, pemilik
2. **Peta Struktur Folder** — tabel fungsi tiap folder/file penting
3. **Setup Lingkungan** — cara clone, install, dan jalankan project
4. **Konvensi Kode** — naming, formatting, style guide yang berlaku
5. **Konvensi Commit** — format Conventional Commits dengan contoh
6. **Alur Kerja** — langkah-langkah kerja agent dari menerima tugas sampai push
7. **Aturan DO** — hal yang harus dilakukan agent
8. **Aturan DON'T** — hal yang tidak boleh dilakukan agent
9. **Checklist Sebelum Commit** — daftar periksa yang harus dicentang
10. **Cara Eskalasi** — kapan dan bagaimana menghubungi pemilik

Gunakan format Markdown yang rapi dengan emoji secukupnya, tabel untuk data terstruktur,
dan code block untuk perintah terminal. Bahasa: Indonesia campuran istilah teknis Inggris.
```

---

## 📖 Contoh Penggunaan

### Input (Variabel yang Diisi)

| Variabel | Nilai |
|----------|-------|
| `{{nama_proyek}}` | "belajar-bareng-api" |
| `{{deskripsi_singkat}}` | "REST API untuk platform pembelajaran online" |
| `{{bahasa_utama}}` | "Go, PostgreSQL, Redis" |
| `{{branch_utama}}` | "main" |
| `{{owner}}` | "Fajar Geran Arifin (@grnlogic)" |

### Contoh Output yang Diharapkan

> AI akan menghasilkan `AGENTS.md` lengkap dengan semua 10 bagian, tabel peta folder, checklist commit, dan contoh pesan commit — siap di-paste ke root repo.

---

## 💡 Catatan dan Tips

- Sesuaikan bagian "Aturan DON'T" dengan risiko spesifik project (misal: jangan sentuh folder `migrations/` tanpa review)
- Review dan edit output AI sebelum di-commit — tambahkan detail yang AI tidak bisa tahu dari template saja
- Perbarui `AGENTS.md` setiap kali ada perubahan besar di arsitektur atau konvensi project
- Simpan `AGENTS.md` di root repo agar AI agent mudah menemukannya saat memulai sesi baru
