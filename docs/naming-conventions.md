# 📏 Konvensi Penamaan File dan Folder

Panduan standar penamaan untuk menjaga konsistensi seluruh repo.

---

## 🔤 Format Utama: kebab-case

Semua nama file dan folder menggunakan **kebab-case**: huruf kecil semua, kata dipisahkan dengan tanda hubung (`-`).

```
✅ Benar          ❌ Salah
-----------       -----------
debugging/        Debugging/
code-review/      CodeReview/
                  code_review/
                  codeReview/
```

---

## 📁 Penamaan Folder

| Aturan | Contoh |
|--------|--------|
| Huruf kecil semua | `penulisan-ilmiah/` bukan `PenulisanIlmiah/` |
| Gunakan `-` sebagai pemisah | `code-review/` bukan `code_review/` |
| Nama deskriptif, 1-3 kata | `agents-md-templates/` |
| Bahasa Inggris untuk folder teknis | `debugging/`, `refactor/`, `workflows/` |
| Bahasa Indonesia boleh untuk konten | `penulisan-ilmiah/`, `laporan/` |

---

## 📄 Penamaan File Prompt

| Aturan | Benar | Salah |
|--------|-------|-------|
| Kebab-case | `analisis-error-stack-trace.md` | `AnalisisError.md` |
| Deskriptif (2-5 kata) | `review-pull-request.md` | `review.md` |
| Tidak ada spasi | `rapikan-abstrak-jurnal.md` | `rapikan abstrak.md` |
| Ekstensi `.md` | `coding-agent-safe.md` | `coding-agent-safe.txt` |
| Tidak ada kata "prompt" di nama file | `analisis-error.md` | `prompt-analisis-error.md` |
| Tidak ada tanggal di nama file | `review-pull-request.md` | `review-pr-2026.md` |

---

## 🏷️ Penamaan Variabel dalam Prompt

Variabel di dalam prompt menggunakan `{{snake_case}}`:

```
✅ Benar                    ❌ Salah
-----------                 -----------
{{bahasa_pemrograman}}      {{BahasaPemrograman}}
{{nama_proyek}}             {{nama-proyek}}
{{stack_trace}}             {{StackTrace}}
{{batas_kata}}              {{batas kata}}
```

---

## 🌿 Penamaan Branch Git

| Tipe | Format | Contoh |
|------|--------|--------|
| Fitur baru | `feat/<deskripsi>` | `feat/prompt-analisis-dataset` |
| Perbaikan | `fix/<deskripsi>` | `fix/abstrak-variabel-typo` |
| Dokumentasi | `docs/<deskripsi>` | `docs/update-contributing-guide` |

---

## ⚠️ Kasus Khusus

| Situasi | Konvensi | Contoh |
|---------|----------|--------|
| File konfigurasi | Gunakan nama standar ekosistem | `.gitignore`, `.editorconfig` |
| File placeholder | `.gitkeep` | Untuk menjaga folder kosong |
| Template | Awali dengan nama template | `prompt-template.md` |
| README per folder | Selalu `README.md` (kapital) | `akademik/README.md` |
| Dokumen panduan | Huruf kapital semua | `AGENTS.md`, `CONTRIBUTING.md` |
