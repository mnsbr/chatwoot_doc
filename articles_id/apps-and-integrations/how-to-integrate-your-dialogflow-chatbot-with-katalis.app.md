# Cara Mengintegrasikan Chatbot Dialogflow dengan Katalis.app

Chatbot bernilai bagi banyak tim keterlibatan pelanggan. Mereka menangani pertanyaan sepele secara efisien dan membebaskan agen manusia untuk fokus pada masalah yang lebih mendesak.

Dialogflow dan Rasa.ai adalah platform NLP (Natural Language Processing) terkemuka untuk membangun chatbot kustom. Dalam panduan ini, kami menjelaskan cara membuat bot di Dialogflow dan mengintegrasikannya dengan Katalis.app dalam hitungan detik.

## Cara Membuat Bot Dialogflow

**Langkah 1.** Buka Dialogflow Console Anda. Kita akan menggunakan Dialogflow Essentials untuk artikel ini. Klik "Create Agent".

**Langkah 2.** Anda perlu membuat intent berdasarkan cara Anda ingin bot merespons. Akan ada 2 intent default di proyek yang disebut "Default Fallback Intent" dan "Default Welcome Intent".

Ini menyelesaikan konfigurasi bot dasar. Mari buat service account dan hubungkan dengan Katalis.app.

Anda juga bisa membuat intent tambahan untuk kasus penggunaan spesifik Anda. Katalis.app juga mendukung intent lanjutan yang memungkinkan handoff agen, pesan interaktif, dll. Lihat: Gulir ke bawah ke "Advanced Intents".

**Langkah 3.** Buat service account. Untuk menghubungkan bot ini dengan Katalis.app, Anda perlu membuat service account di Google Cloud console. Navigasi ke konsol proyek di Google Cloud dengan mengklik Project ID di pengaturan proyek.

Navigasi ke IAM & Admin → Service Accounts. Klik "Create Service Account".

Berikan nama dan deskripsi Service Account.

Untuk memberikan akses, pilih Dialogflow API Client dari dropdown.

Lanjutkan dan klik "Done". Langkah berikutnya adalah membuat key agar bisa dibagikan dengan Katalis.app. Klik service account dan klik tab "Keys". Kemudian, klik "Add Key".

Klik "JSON" dan klik "Create". Ini akan menghasilkan key untuk service account Anda. Unduh key dan simpan untuk digunakan nanti.

## Menyiapkan Integrasi Dialogflow di Katalis.app

Katalis.app memiliki integrasi Dialogflow native. Anda bisa menghubungkan bot dengan Katalis.app dalam dua langkah cepat.

**Langkah 1.** Buka "Settings → Applications → Dialogflow". Klik "Configure".

**Langkah 2.** Klik tombol "Add a new hook". Modal pengaturan akan terbuka. Anda perlu menambahkan "Project ID," "Project Key file," dan inbox untuk membuat hook. Salin isi file key yang diunduh sebelumnya dan tempel ke text area.

Selesai! Integrasi selesai. Uji inbox website untuk melihat apakah bot menangani pertanyaan awal.

## Intent Lanjutan

### Membuat Intent Handoff

Setelah pengguna meminta untuk berbicara dengan agen, Dialogflow harus memberitahu Katalis.app bahwa agen bisa mengambil alih percakapan.

Buat intent bernama "Handoff Intent" dengan frasa pelatihan seperti "Talk to an agent" atau "Speak with an agent," dll. Untuk menangani intent handoff, kita akan membuat respons "Custom Payload":

```json
{
  "action": "handoff"
}
```

Saat memicu intent dengan payload di atas, Katalis.app akan mengubah status percakapan menjadi open dan menyerahkannya ke agen.

### Pesan Interaktif

**Catatan:** Pesan interaktif saat ini hanya didukung di inbox website.

Integrasi Katalis.app-Dialogflow juga mendukung pesan interaktif. Jenis pesan interaktif berikut didukung:

1. Options (follow-up didukung)
2. Cards
3. Articles

### Membuat Intent Pesan Interaktif

Anda bisa membuat pesan interaktif lain dengan mengubah payload seperti yang disebutkan dalam panduan pesan interaktif.

Buat intent dengan frasa pelatihan yang diperlukan dan respons "Custom Payload":

```json
{
  "content_type": "input_select",
  "content": "Select your favorite food from below",
  "content_attributes": {
    "items": [
      { "value": "I like sushi", "title": "Sushi" },
      { "title": "Biryani", "value": "I like biryani" },
      { "title": "Pizza", "value": "I like pizza" }
    ]
  },
  "private": false
}
```

Saat pengguna berinteraksi dengan pesan input dan memilih nilai, nilainya dikembalikan ke Dialogflow. Ini memungkinkan konfigurasi intent follow-up.

### Cara Agen Mentransfer Percakapan Kembali ke Bot Dialogflow

Saat bot Dialogflow terhubung ke inbox, percakapan dibuat dengan status pending alih-alih open. Ini memungkinkan triase awal terjadi melalui bot sebelum percakapan diteruskan ke agen. Saat handoff terjadi, status percakapan diubah menjadi open dan bot berhenti merespons.

Terkadang agen ingin mendorong kembali percakapan yang telah di-handoff ke antrian bot. Mereka bisa melakukan ini dengan mengubah status percakapan kembali ke pending. Ini akan membuat bot mulai merespons percakapan tersebut lagi.
