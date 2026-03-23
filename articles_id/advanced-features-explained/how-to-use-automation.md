# Cara Menggunakan Automasi

Fitur automasi Katalis memperlancar alur kerja tim dengan mengotomatiskan tugas berulang dan menghemat waktu. Fitur ini memungkinkan berbagai tindakan seperti menetapkan label, tim, dan mengarahkan percakapan ke agen yang paling sesuai, memungkinkan tim fokus pada tanggung jawab inti mereka dan menghabiskan lebih sedikit waktu untuk tugas manual.

## Bagaimana Cara Kerja Automasi?

Aturan automasi terdiri dari tiga hal — Event, Conditions, dan Actions. Event adalah pemicu agar automasi berjalan. Conditions adalah kriteria yang harus dipenuhi sebelum actions dieksekusi. Actions adalah tugas yang akan dieksekusi ketika conditions terpenuhi.

### Event Automasi

Event Automasi adalah pemicu yang memulai eksekusi automasi. Katalis saat ini menawarkan empat jenis event:

1. **Conversation created**: Pemicu yang dimulai saat percakapan baru dibuat. Ini termasuk percakapan yang dibuat di semua channel.
2. **Conversation updated**: Pemicu yang dimulai saat percakapan diperbarui.
3. **Message created**: Pemicu yang dimulai saat pesan baru dalam percakapan dibuat.
4. **Conversation opened**: Pemicu yang dimulai saat percakapan yang sebelumnya di-snooze, resolved, atau pending dibuka kembali.

### Conditions Automasi

Conditions adalah kriteria yang harus dipenuhi sebelum actions dilakukan. Mereka dievaluasi dalam urutan yang ditentukan.

Conditions bergantung pada jenis event yang Anda pilih. Berikut daftar lengkapnya:

### Actions Automasi

Actions adalah tugas/proses yang dieksekusi setiap kali conditions terkait terpenuhi. Katalis saat ini mendukung actions berikut:

- Assign to agent
- Assign a team
- Add a label
- Send an email to team
- Send an email transcript
- Mute conversation
- Snooze conversation
- Resolve conversation
- Send Webhook Event
- Cancel
- Send Attachment
- Send a message

Actions ini tersedia terlepas dari Event atau Conditions yang Anda pilih.

## Cara Membuat Aturan Automasi

**Langkah 1.** Buka Settings → Automation. Klik tombol "Add Automation Rule".

**Langkah 2.** Modal pembuatan aturan automasi akan terbuka. Mulai mengisi kolom seperti yang tercantum di bawah:

1. Beri nama automasi Anda untuk referensi mudah nanti.
2. Tambahkan deskripsi (opsional).
3. Pilih event dari menu dropdown.
4. Tambahkan conditions. Gunakan operator equal to atau not equal to untuk mendefinisikan conditions.
5. Tambahkan actions.

Anda juga bisa menambahkan beberapa conditions dan actions. Gunakan operator AND, OR untuk melakukannya.

### Contoh

Anda ingin menetapkan semua percakapan baru ke tim France sales setiap kali Browser language adalah Prancis. Berikut cara membuat aturan automasi untuk ini:

1. Tambahkan nama dan deskripsi.
2. Pilih event sebagai Conversation Created.
3. Tambahkan dua conditions dan gabungkan dengan operator AND. Condition 1: Conversation Status is Open, dan Condition 2: Browser Language is Francais (fr) dari dropdown.
4. Tambahkan action - Assign a team dan pilih tim France sales dari dropdown. (Anda perlu membuat tim terlebih dahulu).

## Cara Menjeda, Mengedit, Menduplikasi, dan Menghapus Aturan Automasi

Daftar aturan Automasi Anda muncul di bawah "Automations". Anda bisa melihat halaman ini dengan membuka Settings → Automation. Anda akan menemukan serangkaian tindakan cepat di sini:

- **Untuk menjeda aturan automasi:** Matikan toggle di bawah kolom "Active".
- **Untuk mengedit aturan:** Klik ikon pensil.
- **Untuk menduplikasi aturan:** Klik ikon salin.
- **Untuk menghapus aturan:** Klik ikon hapus.
