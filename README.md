# puppeteer-heroku-buildpack

Menginstal dependensi yang diperlukan untuk menjalankan Puppeteer di heroku. Pastikan untuk menyertakan `{ args: ['--no-sandbox'] }` Panggil Ke Dalam `puppeteer.launch`. 

Puppeteer default untuk `headless: true` didalam `puppeteer.launch` dan ini tidak boleh diubah. Heroku tidak memiliki GUI untuk menunjukkan chrome saat dijalankan `headless: false` dan Heroku akan melempar Errorr.

Jika Anda ingin menggunakan Puppeteer dengan firefox alih-alih chrome, gunakan buildpack ini sebagai gantinya:
https://github.com/jontewks/heroku-buildpack-puppeteer-firefox

## Usage

Untuk menggunakan versi stabil terbaru, jalankan:

```sh-session
$ heroku buildpacks:add ismailsamudra/puppeteer
```

Atau gunakan kode sumber di repositori ini:

```sh-session
$ heroku buildpacks:add https://github.com/ismailsamudra/puppeteer-heroku-buildpack.git
```

### Additional language support
Jika Anda memerlukan dukungan untuk font Jepang, Cina, atau Korea, fork buildpack ini telah dibuat untuk menyertakannya juga:
https://github.com/CoffeeAndCode/puppeteer-heroku-buildpack

## Issues

Masalah umum yang sering dialami orang adalah masalah cache dengan heroku. Seringkali ketika Anda mulai melihat kesalahan bahwa chrome tidak dapat dimulai dan beberapa perpustakaan hilang, Anda dapat menyelesaikannya dengan mengosongkan cache heroku Anda. Petunjuk untuk itu dapat ditemukan di sini:
https://help.heroku.com/18PI5RSY/how-do-i-clear-the-build-cache

Jika Anda masih mengalami masalah dengan buildpack ini setelah melakukan hal di atas, silakan buka masalah pada repo ini dan/atau kirimkan PR yang menyelesaikannya. Versi chrome yang berbeda memiliki dependensi yang berbeda sehingga beberapa masalah dapat muncul tanpa sepengetahuan saya. Terima kasih!
