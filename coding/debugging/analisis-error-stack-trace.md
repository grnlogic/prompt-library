---
judul: "Analisis Error dan Stack Trace"
kategori: coding
tags: [debugging, error, stack-trace, analisis, troubleshooting]
model: GPT-4, Claude 3.5 Sonnet, Gemini 1.5 Pro
versi: 1.0
tanggal_update: 2026-10-01
---

# Analisis Error dan Stack Trace

## 🎯 Tujuan

Menganalisis pesan error beserta stack trace untuk mengidentifikasi akar masalah, menjelaskan penyebabnya dalam bahasa yang mudah dipahami, dan memberikan langkah solusi yang actionable.

---

## 📌 Kapan Dipakai

- Saat menemui error yang belum pernah dijumpai sebelumnya
- Saat stack trace terlalu panjang dan membingungkan
- Saat error muncul di library pihak ketiga dan sulit dilacak asalnya
- Saat debugging di environment produksi dengan log terbatas

---

## 🔧 Variabel yang Harus Diisi

| Variabel | Deskripsi | Contoh Isian |
|----------|-----------|--------------|
| `{{bahasa_pemrograman}}` | Bahasa pemrograman yang dipakai | "Python 3.11", "TypeScript", "Java 17" |
| `{{framework}}` | Framework / library yang digunakan | "FastAPI", "Next.js", "Spring Boot" |
| `{{pesan_error}}` | Pesan error lengkap | (paste error message) |
| `{{stack_trace}}` | Stack trace lengkap | (paste stack trace) |
| `{{kode_relevan}}` | Potongan kode di sekitar error | (paste kode yang bermasalah) |
| `{{konteks}}` | Apa yang sedang dilakukan saat error | "saat upload file > 10MB" |

---

## 💬 Prompt

```
Kamu adalah senior software engineer yang ahli di {{bahasa_pemrograman}} dan {{framework}}.

Saya menemui error berikut:

**Pesan Error:**
```
{{pesan_error}}
```

**Stack Trace:**
```
{{stack_trace}}
```

**Kode yang Bermasalah:**
```{{bahasa_pemrograman}}
{{kode_relevan}}
```

**Konteks:** {{konteks}}

Tolong lakukan analisis dengan struktur berikut:

### 1. 🔍 Akar Masalah
Jelaskan apa penyebab sesungguhnya dari error ini (bukan sekadar apa yang tertulis di pesan error).

### 2. 📍 Lokasi Error
Tunjukkan baris / fungsi mana yang menjadi titik masalah utama.

### 3. ✅ Solusi yang Disarankan
Berikan minimal 2 solusi dengan kode yang bisa langsung dipakai, urutkan dari yang paling mudah ke yang paling robust.

### 4. 🛡️ Pencegahan
Jelaskan bagaimana menghindari error serupa di masa depan.
```

---

## 📖 Contoh Penggunaan

### Input (Variabel yang Diisi)

| Variabel | Nilai |
|----------|-------|
| `{{bahasa_pemrograman}}` | "Python 3.11" |
| `{{framework}}` | "FastAPI" |
| `{{konteks}}` | "saat endpoint menerima request POST" |

### Contoh Output yang Diharapkan

> **Akar Masalah:** `KeyError: 'user_id'` terjadi karena request body yang masuk tidak divalidasi terlebih dahulu. FastAPI menggunakan Pydantic untuk validasi, tapi field `user_id` tidak didefinisikan sebagai required di model...
>
> **Solusi 1 (cepat):** Tambahkan `.get('user_id')` dengan default value...
> **Solusi 2 (robust):** Definisikan Pydantic model yang proper...

---

## 💡 Catatan dan Tips

- Sertakan **seluruh** stack trace, bukan hanya baris terakhir — AI membutuhkan konteks penuh
- Jika error terjadi di library pihak ketiga, sertakan versi library tersebut
- Untuk error intermittent, tambahkan kapan error terjadi (frekuensi, pattern)
- Hapus informasi sensitif (token, password, URL internal) dari kode sebelum di-paste
