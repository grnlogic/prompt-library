# 🤖 Agents

Kumpulan prompt untuk membangun, mengonfigurasi, dan mendokumentasikan AI agent: system prompt, workflow otomatis, dan template AGENTS.md.

---

## 📂 Subfolder

| Folder | Deskripsi |
|--------|-----------|
| `system-prompts/` | System prompt siap pakai untuk berbagai jenis AI agent |
| `workflows/` | Alur kerja multi-langkah untuk agent yang bekerja dalam pipeline |
| `agents-md-templates/` | Template `AGENTS.md` untuk project baru |

---

## 📋 Daftar Prompt

| File | Deskripsi | Model yang Direkomendasikan |
|------|-----------|---------------------------|
| [`system-prompts/coding-agent-safe.md`](./system-prompts/coding-agent-safe.md) | System prompt coding agent dengan batasan scope yang ketat | GPT-4, Claude 3.5, Gemini 1.5 |
| [`agents-md-templates/generic-agents-md.md`](./agents-md-templates/generic-agents-md.md) | Prompt untuk generate AGENTS.md untuk project baru | GPT-4, Claude 3.5 |

---

## 💡 Tips Penggunaan

- System prompt yang baik mendefinisikan **peran**, **batas kerja**, dan **cara eskalasi** secara eksplisit
- Review dan test system prompt sebelum dipakai di lingkungan produksi
- Perbarui system prompt secara berkala seiring perubahan kebutuhan project
