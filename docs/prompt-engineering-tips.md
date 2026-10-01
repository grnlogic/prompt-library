# 💡 Tips Menulis Prompt yang Efektif

Panduan singkat untuk membuat prompt yang menghasilkan output berkualitas tinggi dari AI.

---

## 1. 🎯 Berikan Peran yang Jelas

Mulai prompt dengan mendefinisikan siapa AI dalam konteks ini. Peran yang spesifik menghasilkan respons yang lebih relevan dan konsisten.

```
❌ Kurang baik: "Tolong review kode saya."
✅ Lebih baik: "Kamu adalah senior software engineer berpengalaman di Python dan FastAPI. Review kode berikut..."
```

---

## 2. 📐 Definisikan Format Output

Jika kamu tahu format output yang diinginkan, sebutkan secara eksplisit. AI tidak bisa menebak preferensimu.

```
❌ Kurang baik: "Jelaskan error ini."
✅ Lebih baik: "Jelaskan error ini dalam format: (1) Akar Masalah, (2) Solusi, (3) Cara Mencegah."
```

---

## 3. 🔧 Gunakan Variabel {{...}}

Pisahkan bagian yang bisa berubah dari bagian yang tetap. Ini membuat prompt reusable dan mudah dimodifikasi.

```
"Buatkan unit test untuk fungsi {{nama_fungsi}} dalam bahasa {{bahasa}} menggunakan framework {{framework}}."
```

---

## 4. 📝 Sertakan Konteks yang Cukup

AI tidak punya konteks di luar yang kamu berikan. Jangan asumsikan AI "tahu" background proyekmu.

```
❌ Kurang baik: "Kenapa ini tidak berjalan?" (tanpa kode, tanpa error)
✅ Lebih baik: (sertakan kode, pesan error, stack trace, dan konteks apa yang sedang dilakukan)
```

---

## 5. 🎚️ Tentukan Tingkat Detail

Sebutkan seberapa detail output yang kamu butuhkan. Tanpa ini, AI akan menebak level pembaca.

```
"Jelaskan konsep ini untuk audiens yang sudah familiar dengan programming tapi baru dengan machine learning."
"Berikan penjelasan teknis mendalam, saya senior engineer."
```

---

## 6. ✂️ Satu Prompt, Satu Tujuan

Prompt yang mencoba melakukan terlalu banyak hal sekaligus menghasilkan output yang tidak fokus.

```
❌ Kurang baik: "Debug kode ini, lalu refactor, lalu buatkan dokumentasinya, dan tambahkan unit test."
✅ Lebih baik: Pecah menjadi 4 prompt terpisah, jalankan berurutan.
```

---

## 7. 🔄 Iterasi, Bukan Selesai Sekali

Prompt pertama jarang langsung sempurna. Gunakan follow-up untuk menyempurnakan:
- "Buat lebih singkat"
- "Fokus hanya pada bagian X"
- "Ubah tone menjadi lebih formal"
- "Tambahkan contoh untuk poin ke-2"

---

## 8. 🚫 Hindari Instruksi Negatif Tunggal

Instruksi "jangan lakukan X" kurang efektif dibanding instruksi positif tentang apa yang harus dilakukan.

```
❌ Kurang baik: "Jangan gunakan bahasa yang terlalu teknis."
✅ Lebih baik: "Gunakan bahasa yang mudah dipahami oleh non-programmer."
```

---

## 9. 📋 Gunakan Contoh (Few-Shot Prompting)

Jika output yang diinginkan sulit dideskripsikan, tunjukkan contohnya langsung.

```
"Ubah judul berikut ke format yang lebih menarik. 
Contoh: 'Cara Debug Python' → 'Berhenti Menebak: Cara Debug Python yang Benar'
Sekarang ubah: '{{judul_asli}}'"
```

---

## 10. 🔐 Jangan Sertakan Data Sensitif

Sebelum mengirim prompt ke AI (terutama layanan cloud):
- Hapus API key, token, password
- Anonimkan data pengguna (nama, email, nomor ID)
- Ganti URL internal dengan placeholder
- Jangan paste konten dari file `.env`

---

## 📚 Referensi Lanjutan

- [Prompt Engineering Guide](https://www.promptingguide.ai/)
- [OpenAI Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic's Claude Prompting Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
