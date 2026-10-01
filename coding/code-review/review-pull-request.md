---
judul: "Review Pull Request Komprehensif"
kategori: coding
tags: [code-review, pull-request, pr, kualitas-kode, best-practices]
model: GPT-4, Claude 3.5 Sonnet, Gemini 1.5 Pro
versi: 1.0
tanggal_update: 2026-10-01
---

# Review Pull Request Komprehensif

## 🎯 Tujuan

Melakukan code review menyeluruh terhadap sebuah Pull Request: memeriksa kebenaran logika, keamanan, performa, keterbacaan, dan kepatuhan terhadap standar tim.

---

## 📌 Kapan Dipakai

- Saat menjadi reviewer PR dan butuh panduan sistematis
- Saat ingin self-review sebelum minta review ke tim
- Saat onboarding anggota baru yang belum terbiasa dengan standar tim
- Saat PR besar dan sulit ditinjau secara manual

---

## 🔧 Variabel yang Harus Diisi

| Variabel | Deskripsi | Contoh Isian |
|----------|-----------|--------------|
| `{{bahasa_pemrograman}}` | Bahasa utama dalam PR | "TypeScript", "Python", "Go" |
| `{{deskripsi_pr}}` | Deskripsi atau judul PR | "feat: tambah autentikasi JWT" |
| `{{diff_kode}}` | Git diff atau kode yang berubah | (paste output `git diff`) |
| `{{standar_tim}}` | Standar atau panduan tim jika ada | "ESLint Airbnb, max 80 char/baris" |
| `{{fokus_review}}` | Aspek yang paling ingin difokuskan | "keamanan dan performa" |

---

## 💬 Prompt

```
Kamu adalah senior software engineer berpengalaman dalam {{bahasa_pemrograman}} yang bertugas mereview Pull Request berikut.

**Deskripsi PR:** {{deskripsi_pr}}

**Standar Tim:** {{standar_tim}}

**Kode yang Berubah (diff):**
```
{{diff_kode}}
```

**Fokus Review:** {{fokus_review}}

Lakukan review menyeluruh dengan struktur berikut:

## 🟢 Yang Sudah Baik
Sebutkan hal-hal positif dalam kode ini (minimal 2).

## 🔴 Masalah Kritis (Harus Diperbaiki)
Masalah yang bisa menyebabkan bug, security hole, atau data loss. Sertakan baris kode spesifik dan solusi yang disarankan.

## 🟡 Saran Peningkatan (Nice to Have)
Perubahan yang tidak wajib tapi meningkatkan kualitas kode.

## 📝 Komentar Umum
Catatan tentang arsitektur, keterbacaan, atau hal lain yang perlu didiskusikan.

## ✅ Verdict
- [ ] Approve — siap merge
- [ ] Request Changes — perlu perbaikan sebelum merge
- [ ] Needs Discussion — perlu diskusi lebih lanjut
```

---

## 📖 Contoh Penggunaan

### Input (Variabel yang Diisi)

| Variabel | Nilai |
|----------|-------|
| `{{bahasa_pemrograman}}` | "TypeScript (Next.js 14)" |
| `{{deskripsi_pr}}` | "feat: tambah endpoint login dengan JWT" |
| `{{standar_tim}}` | "ESLint Airbnb, no any types, semua error harus di-handle" |
| `{{fokus_review}}` | "keamanan autentikasi dan error handling" |

### Contoh Output yang Diharapkan

> **🔴 Masalah Kritis:**
> - Baris 42: JWT secret dibaca langsung dari `process.env.JWT_SECRET` tanpa validasi — jika env tidak diset, server akan crash silently. Tambahkan guard: `if (!process.env.JWT_SECRET) throw new Error(...)` di startup.
> - Baris 67: Password dibandingkan dengan `===` bukan `bcrypt.compare` — rentan timing attack.

---

## 💡 Catatan dan Tips

- Pastikan diff yang di-paste **tidak mengandung secret** (env value, token, dsb.)
- Untuk PR besar (>500 baris), review per file atau per fitur
- Sebutkan konteks bisnis jika relevan — reviewer perlu tahu *mengapa* kode ditulis seperti itu
- Gunakan hasil review sebagai panduan diskusi, bukan keputusan final mutlak
