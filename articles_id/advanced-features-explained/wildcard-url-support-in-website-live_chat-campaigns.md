# Dukungan URL Wildcard di Campaign Website Live-Chat

Campaign website live-chat mendukung pola URL wildcard. Saat membangun pola URL, pertimbangkan perilaku berikut.

Di Katalis.app, setiap pola URL harus dimulai dengan `http://` atau `https://`.

## Menjalankan Campaign di URL yang Tepat

Jika Anda menambahkan URL yang tepat seperti `https://katalis.app/app`, maka URL dengan trailing slash atau parameter URL atau parameter hash tidak akan cocok. Beberapa contoh definisi pencocokan tepat adalah:

- `https://katalis.app/app` akan cocok dengan `https://katalis.app/app/` atau `https://katalis.app/app?test_param=1`
- `https://katalis.app/app?test_param=test_value` tidak akan cocok dengan `https://katalis.app/app` atau `https://katalis.app/app#test_hash_param`

## Menjalankan Campaign dengan Mengabaikan Parameter URL

Untuk mengabaikan parameter URL atau parameter hash, Anda bisa menambahkan trailing slash di URL. Contoh: `https://katalis.app/app/` akan cocok dengan semua URL berikut:

- `https://katalis.app/app/`
- `https://katalis.app/app`
- `https://katalis.app/app/?test=1`
- `https://katalis.app/app/#test`

## Menjalankan Campaign di Semua Sub-Direktori

Anda bisa menggunakan karakter `*` di URL jika ingin mencocokkan semua sub-direktori. Contoh: `https://katalis.app/*` akan cocok dengan URL berikut:

- `https://katalis.app/`
- `https://katalis.app/app`
- `https://katalis.app/app/subdirectory`

## Menjalankan Campaign di Semua Subdomain

Untuk mencocokkan domain saat ini dan subdomain, Anda bisa menggunakan pola `{*.}?` di URL. Contoh: `https://{*.}?katalis.app/` akan cocok dengan URL berikut:

- `https://katalis.app`
- `https://app.katalis.app`
- `https://www.katalis.app`
