
# Menyiapkan Autentikasi SAML

Ini adalah panduan untuk menyiapkan autentikasi SAML untuk akun Anda. Panduan ini mengasumsikan Anda sudah memiliki IdP yang berfungsi.

Sebelum memulai, ada beberapa hal yang perlu diperhatikan:

- Setelah SAML diaktifkan, pengguna Anda tidak akan bisa mengakses Katalis.app dengan password mereka. Menonaktifkan SAML akan mengembalikan perilaku ini.
- Jika pengguna merupakan bagian dari beberapa akun, dan salah satu akun memiliki pengaturan SAML, mereka harus login melalui SAML IdP saja. Sebaiknya batasi pengguna ke domain Anda saja.

## Menyiapkan SAML

Anda bisa menemukan pengaturan SAML di Settings > Security. Berikut pengaturan yang perlu Anda ketahui:

- **SSO URL**: Alamat HTTPS spesifik pada Identity Provider di mana login SAML dimulai; aplikasi Anda mengarahkan pengguna ke sini untuk autentikasi. Anggap ini sebagai "login endpoint" IdP yang menerima SAML AuthnRequest dan memulai alur SSO.

- **Identity Provider Entity ID**: Pengidentifikasi unik global (biasanya string berbentuk URI) yang menamai Identity Provider dalam metadata SAML. Service Provider Anda menggunakannya untuk memilih konfigurasi IdP yang tepat dan untuk memvalidasi bahwa pesan SAML yang masuk benar-benar mengklaim berasal dari IdP tersebut.

- **Signing Certificate**: Sertifikat publik X.509 IdP yang digunakan untuk menandatangani respons/assertion SAML. Service Provider Anda menyimpan sertifikat ini dan memverifikasi tanda tangan dengannya, memastikan pesan tidak diubah dan benar-benar berasal dari IdP.

Setelah diatur, Anda akan menemukan detail yang diperlukan untuk mendaftarkan Katalis.app sebagai Service Provider (SP) pada provider SAML Anda. Berikut detail yang akan Anda dapatkan:

- **ACS URL**: Endpoint Assertion Consumer Service pada Service Provider yang menerima SAML Response dari IdP. Setelah pengguna terautentikasi, IdP mengirimkan assertion yang ditandatangani ke URL HTTPS ini, di mana aplikasi Anda memvalidasinya dan membuat sesi.

- **SP Entity ID**: Pengidentifikasi unik (sering berupa URI) untuk Service Provider dalam metadata SAML. IdP menggunakan nilai ini untuk memastikan respons diterbitkan untuk aplikasi yang benar dan untuk memilih ACS URL dan pengaturan yang tepat.

Jika Anda memerlukan informasi ini sebelumnya, berikut formatnya:

- ACS URL: `<instalasi-Katalis.app-anda>/omniauth/saml/callback?account_id=<id-akun-anda>`
- SP Entity ID: `<instalasi-Katalis.app-anda>/saml/sp/<id-akun-anda>`

## Pemetaan Data

Pemetaan atribut berikut harus dikonfigurasi di identity provider Anda:

- email
- first_name
- last_name

Saat pengguna login untuk pertama kali, informasi ini digunakan untuk membuat pengguna untuk mereka. Informasi tidak diperbarui setelahnya.

## Autentikasi

Anda bisa navigasi ke link https://app.katalis.app/app/login/sso untuk melihat formulir login SAML. Cukup masukkan alamat email dan aplikasi akan mengarahkan Anda ke provider SAML yang dikonfigurasi.
