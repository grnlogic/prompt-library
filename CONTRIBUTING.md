# Cara Berkontribusi ke Prompt Library

Terima kasih sudah mau berkontribusi! 🙌  
Panduan ini menjelaskan cara menambahkan prompt baru, melaporkan masalah, atau memperbaiki prompt yang sudah ada.

---

## 📋 Sebelum Mulai

1. Pastikan kamu sudah membaca [`AGENTS.md`](./AGENTS.md) untuk memahami konvensi dan aturan repo ini.
2. Cek apakah prompt yang ingin kamu tambahkan belum ada di kategori yang sesuai.
3. Gunakan [`templates/prompt-template.md`](./templates/prompt-template.md) sebagai dasar prompt baru.

---

## 🚀 Alur Kontribusi

### 1. Fork & Clone

```bash
# Fork repo di GitHub, lalu clone fork kamu
git clone git@github.com:<username-kamu>/prompt-library.git
cd prompt-library
```

### 2. Buat Branch Baru

Gunakan format: `feat/nama-prompt` atau `fix/nama-prompt`

```bash
git checkout -b feat/prompt-analisis-dataset
```

### 3. Tambah / Edit Prompt

- Salin `templates/prompt-template.md` ke folder yang sesuai
- Isi semua bagian front matter dan konten
- Ikuti aturan penamaan: `kebab-case`, deskriptif, bahasa Inggris

```bash
cp templates/prompt-template.md coding/debugging/nama-prompt-baru.md
```

### 4. Commit

Gunakan format [Conventional Commits](https://www.conventionalcommits.org/):

```bash
git add .
git commit -m "feat(coding): tambah prompt analisis dataset pandas"
```

### 5. Push & Buat Pull Request

```bash
git push origin feat/prompt-analisis-dataset
```

Buat PR di GitHub → isi PR template → tunggu review.

---

## 📝 Format Prompt

Setiap prompt **wajib** memiliki:

| Bagian | Wajib | Keterangan |
|--------|-------|------------|
| Front matter | ✅ | judul, kategori, tags, model, versi, tanggal |
| Tujuan | ✅ | 1-2 kalimat |
| Kapan dipakai | ✅ | konteks penggunaan |
| Variabel | ✅ jika ada | format `{{nama_variabel}}` |
| Prompt (code block) | ✅ | siap copy-paste |
| Contoh | ✅ | minimal 1 contoh input + output |
| Catatan | opsional | tips tambahan |

---

## 🚫 Yang Tidak Boleh

- ❌ Jangan tambahkan data pribadi, API key, token, atau informasi sensitif
- ❌ Jangan ubah `LICENSE` tanpa diskusi
- ❌ Jangan hapus prompt milik orang lain tanpa alasan jelas
- ❌ Jangan force push ke `main`

---

## 💬 Punya Pertanyaan?

Buka [Discussion](https://github.com/grnlogic/prompt-library/discussions) atau hubungi [@grnlogic](https://github.com/grnlogic).
