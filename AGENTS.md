# 🤖 AGENTS.md — Panduan untuk AI Agent di Prompt Library

> **Repo:** `grnlogic/prompt-library`
> **Pemilik:** Fajar Geran Arifin ([@grnlogic](https://github.com/grnlogic))
> **Branch Utama:** `main`
> **Terakhir Diperbarui:** 2026-10-01

---

## 📖 1. Ringkasan Repo

**Prompt Library** adalah koleksi prompt siap pakai yang dikurasi dan terstruktur, dirancang untuk membantu developer, mahasiswa, dan builder bekerja lebih efisien bersama AI. Setiap prompt menggunakan template standar dengan variabel `{{...}}` yang bisa langsung diisi dan dijalankan.

**Tiga kategori utama:**
| Kategori | Deskripsi |
|----------|-----------|
| 🎓 `akademik/` | Prompt untuk penulisan ilmiah, laporan, dan presentasi akademik |
| 💻 `coding/` | Prompt untuk debugging, refactor, code review, dan dokumentasi kode |
| 🤖 `agents/` | System prompt, workflow, dan template AGENTS.md untuk AI agent |

---

## 🗂️ 2. Peta Struktur Folder

```
prompt-library/
├── AGENTS.md                    ← Panduan ini (untuk AI agent)
├── README.md                    ← Dokumentasi utama (untuk manusia)
├── LICENSE                      ← MIT License
├── CONTRIBUTING.md              ← Cara berkontribusi
├── CHANGELOG.md                 ← Riwayat perubahan
├── .gitignore
├── .github/
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── ISSUE_TEMPLATE/
│       ├── new-prompt.md        ← Template issue: prompt baru
│       └── improve-prompt.md   ← Template issue: perbaikan prompt
├── akademik/
│   ├── README.md
│   ├── penulisan-ilmiah/        ← Prompt abstrak, makalah, esai
│   ├── laporan/                 ← Prompt laporan PKL, penelitian
│   └── presentasi/              ← Prompt slide, narasi presentasi
├── coding/
│   ├── README.md
│   ├── debugging/               ← Analisis error, stack trace
│   ├── refactor/                ← Perbaikan kualitas kode
│   ├── code-review/             ← Review PR dan kode
│   └── dokumentasi/             ← Docstring, README otomatis
├── agents/
│   ├── README.md
│   ├── system-prompts/          ← System prompt siap pakai
│   ├── workflows/               ← Alur kerja multi-langkah
│   └── agents-md-templates/    ← Template AGENTS.md untuk project baru
├── templates/
│   └── prompt-template.md       ← Template standar untuk prompt baru
└── docs/
    ├── prompt-engineering-tips.md
    └── naming-conventions.md
```

### Fungsi Tiap Folder

| Folder | Fungsi | Boleh Diubah Agent? |
|--------|--------|---------------------|
| `akademik/` | Prompt untuk konteks akademik | ✅ Tambah/edit prompt |
| `coding/` | Prompt untuk workflow coding | ✅ Tambah/edit prompt |
| `agents/` | Prompt dan template untuk AI agent | ✅ Tambah/edit prompt |
| `templates/` | Template master — standar seluruh repo | ⚠️ Hanya jika diminta pemilik |
| `docs/` | Dokumentasi panduan | ✅ Tambah/perbaiki |
| `.github/` | Template GitHub | ⚠️ Hanya jika diminta pemilik |
| `LICENSE` | Lisensi MIT | ❌ Jangan diubah |
| `CHANGELOG.md` | Riwayat versi | ✅ Selalu update setelah commit |

---

## ➕ 3. Cara Menambah Prompt Baru

Ikuti langkah berikut secara berurutan:

**Step 1 — Tentukan kategori**
```
akademik/  →  konten akademik (abstrak, laporan, esai)
coding/    →  workflow coding (debug, refactor, review)
agents/    →  AI agent & system prompt
```

**Step 2 — Salin template**
```bash
cp templates/prompt-template.md <kategori>/<subfolder>/<nama-prompt>.md
```

**Step 3 — Isi semua bagian template**
- Front matter: judul, kategori, tags, model, versi, tanggal
- Tujuan, kapan dipakai, variabel
- Prompt dalam code block
- Minimal 1 contoh input + output
- Catatan dan tips

**Step 4 — Perbarui README kategori**
Tambahkan baris di tabel daftar prompt di `<kategori>/README.md`.

**Step 5 — Perbarui CHANGELOG.md**
Tambahkan entri di bagian `[Unreleased]`:
```
- `kategori/subfolder/nama-prompt.md` — deskripsi singkat
```

**Step 6 — Commit**
```bash
git add .
git commit -m "feat(kategori): tambah prompt <judul-singkat>"
```

---

## 🏷️ 4. Konvensi Penamaan File

Semua file menggunakan **kebab-case** dalam **bahasa Inggris** (untuk nama file/folder) dan **bahasa Indonesia** untuk konten di dalam file.

| ✅ Benar | ❌ Salah |
|---------|---------|
| `analisis-error-stack-trace.md` | `AnalisisError.md` |
| `review-pull-request.md` | `review PR.md` |
| `rapikan-abstrak-jurnal.md` | `rapikan abstrak.md` |
| `coding-agent-safe.md` | `CodingAgentSafe.md` |
| `generic-agents-md.md` | `generic_agents_md.md` |

**Aturan tambahan:**
- Nama file: deskriptif, 2-5 kata, semua huruf kecil
- Subfolder baru: konsultasikan dengan pemilik dulu
- Tidak boleh ada spasi di nama file/folder
- Gunakan `-` bukan `_` sebagai pemisah

---

## ✍️ 5. Aturan Menulis Prompt

Setiap prompt yang ditambahkan **wajib** memenuhi kriteria berikut:

| Kriteria | Detail |
|----------|--------|
| **Spesifik** | Prompt harus memiliki tujuan tunggal yang jelas, bukan multi-tujuan |
| **Ada variabel** | Gunakan `{{nama_variabel}}` untuk bagian yang perlu dikustomisasi |
| **Ada contoh** | Minimal 1 contoh input + output nyata atau representatif |
| **Tidak ada data sensitif** | Jangan sertakan API key, password, URL internal, atau data pribadi nyata |
| **Pakai template** | Ikuti struktur `templates/prompt-template.md` |
| **Front matter lengkap** | Semua field wajib terisi (judul, kategori, tags, model, versi, tanggal) |

**Yang membuat prompt bagus:**
- Menyebutkan **peran AI** di awal ("Kamu adalah...")
- Mendefinisikan **format output** yang diinginkan
- Memberikan **konteks yang cukup** tanpa berlebihan
- Menggunakan `{{variabel}}` untuk semua bagian yang bisa berubah

---

## 📝 6. Konvensi Commit

Repo ini menggunakan [Conventional Commits](https://www.conventionalcommits.org/).

### Format
```
<type>(<scope>): <deskripsi singkat>
```

### Type yang Valid

| Type | Kapan Dipakai | Contoh |
|------|---------------|--------|
| `feat` | Menambah prompt atau fitur baru | `feat(coding): tambah prompt refactor class` |
| `fix` | Memperbaiki prompt yang bermasalah | `fix(akademik): perbaiki variabel yang salah` |
| `docs` | Update dokumentasi (README, AGENTS.md) | `docs: perbarui cara kontribusi di CONTRIBUTING.md` |
| `chore` | Maintenance (gitignore, struktur) | `chore: tambah .gitkeep di folder kosong` |
| `style` | Format, typo, tanpa ubah makna | `style(agents): perbaiki typo di coding-agent-safe.md` |

### Contoh Commit yang Baik
```bash
feat(coding): tambah prompt analisis kompleksitas algoritma
fix(akademik): perbaiki contoh output di rapikan-abstrak-jurnal.md
docs: update README dengan bagian cara berkontribusi
chore: perbarui .gitignore untuk menambah *.tmp
```

### Contoh Commit yang Buruk
```bash
update file          # terlalu umum
fix stuff            # tidak informatif
WIP                  # jangan commit WIP ke main
tambah prompt baru   # tidak pakai format conventional
```

---

## ✅ 7. Do dan Don't untuk AI Agent

### ✅ DO — Yang Harus Dilakukan

- **Baca AGENTS.md dan README** sebelum memulai pekerjaan apapun
- **Gunakan template** `templates/prompt-template.md` untuk setiap prompt baru
- **Perbarui CHANGELOG.md** setiap kali menambah atau mengubah prompt
- **Perbarui README** di folder kategori yang terpengaruh
- **Gunakan format Conventional Commits** di setiap commit
- **Minta konfirmasi** sebelum mengubah file di `templates/` atau `.github/`
- **Laporkan** jika menemukan prompt yang sudah usang atau tidak akurat

### ❌ DON'T — Yang Tidak Boleh Dilakukan

- ❌ **Jangan hapus prompt lama** tanpa instruksi eksplisit dari pemilik
- ❌ **Jangan ubah `LICENSE`** — hanya pemilik yang bisa mengubahnya
- ❌ **Jangan force push** (`git push --force`) ke branch manapun
- ❌ **Jangan commit secret** — API key, token, password, data pribadi
- ❌ **Jangan ubah front matter** prompt milik orang lain tanpa alasan jelas
- ❌ **Jangan buat subfolder baru** tanpa konfirmasi pemilik
- ❌ **Jangan merge ke main** tanpa melalui PR
- ❌ **Jangan asumsikan** konteks yang tidak tertulis — tanya jika tidak jelas

---

## 📋 8. Checklist Sebelum Commit

Centang semua sebelum menjalankan `git commit`:

- [ ] Prompt menggunakan `templates/prompt-template.md` sebagai dasar
- [ ] Front matter terisi lengkap (judul, kategori, tags, model, versi, tanggal)
- [ ] Ada minimal 1 contoh input + output nyata
- [ ] Semua `{{variabel}}` terdokumentasi di tabel variabel
- [ ] **Tidak ada** data sensitif (API key, password, URL internal)
- [ ] Nama file menggunakan kebab-case
- [ ] README di folder kategori sudah diperbarui
- [ ] CHANGELOG.md sudah diperbarui di bagian `[Unreleased]`
- [ ] Pesan commit mengikuti format Conventional Commits
- [ ] `git status` tidak menunjukkan file sensitif yang tidak disengaja

---

## 💬 9. Cara Menghubungi / Memberi Masukan

| Saluran | Kapan Dipakai |
|---------|---------------|
| [GitHub Issues](https://github.com/grnlogic/prompt-library/issues) | Bug, prompt yang tidak bekerja, permintaan fitur |
| [GitHub Discussions](https://github.com/grnlogic/prompt-library/discussions) | Ide, diskusi umum, feedback |
| [GitHub Profile @grnlogic](https://github.com/grnlogic) | Kontak langsung pemilik |

Untuk masalah keamanan (jika ada data sensitif yang tidak sengaja ter-commit), buat issue **private** atau hubungi langsung lewat profil GitHub.
