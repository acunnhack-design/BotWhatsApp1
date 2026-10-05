# XCODE — WhatsApp Pairing + Telegram

## 1. Konfigurasi
Edit `settings/.config` sebelum menjalankan:

```ini
TOKEN_BOT=PASTE_TOKEN_TELEGRAM_BARU_DI_SINI
OWNER_ID=PASTE_TELEGRAM_USER_ID_DI_SINI
REQUIRED_CHANNEL_LINK=https://t.me/metagzz
```

Jangan commit atau membagikan token Telegram.

## 2. Jalankan lokal / VPS

```bash
npm install
npm start
```

Perintah WhatsApp pairing yang tersedia di source adalah `/addbot`. Saat diminta nomor, gunakan format internasional tanpa tanda `+`, misalnya `628xxxxxxxxxx`.

## 3. Pairing WhatsApp

1. Jalankan bot.
2. Buka bot Telegram sebagai owner.
3. Jalankan `/addbot`.
4. Masukkan nomor WhatsApp dalam format internasional.
5. Ambil pairing code yang dikirim bot.
6. WhatsApp → Linked Devices → Link a device → Link with phone number, lalu masukkan code.

Session/auth WhatsApp harus disimpan pada filesystem persistent. Jangan gunakan hosting serverless/ephemeral untuk bot ini.

## 4. Hosting gratis

Pilihan yang cocok adalah layanan yang menyediakan proses Node.js yang tetap hidup dan persistent storage. Hindari static hosting seperti GitHub Pages/InfinityFree untuk proses Node.js/WhatsApp.

Untuk layanan free-tier, cek batas CPU/RAM/sleep dan persistent disk sebelum deployment karena kebijakan free-tier dapat berubah.

## 5. Security

Token Telegram yang pernah diposting di chat harus di-revoke/regenerate lewat BotFather sebelum deployment. Setelah itu masukkan token baru hanya ke `settings/.config` atau environment variable.
