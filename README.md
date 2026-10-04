# GENERATE-FOTO-PASPORT-DAN-KARTU-PERDANA
## n8n workflow

`n8n-workflow.json` — Telegram (3 gambar) → AI Image ×2 → Google Drive (folder baru bertimestamp di dalam folder master).

Import lewat n8n: *Workflows → Import from File*. Setup:

1. Buat Data Table `telegram_image_buffer` (`chat_id` string, `message_id` number, `file_id` string, `received_at` number), lalu pilih di 3 node *Buffer*.
2. Isi prompt cabang 1 & 2, model, dan `master_folder_id` di node **Config**.
3. Pasang credential Telegram, OpenAI, Google Drive.
4. Activate workflow (jangan diuji dengan Execute manual — satu album = 3 execution).

Urutan kirim gambar = peran: 1 paspor, 2 kartu provider, 3 gambar ketiga (ubah di node *Combine Binaries*).
