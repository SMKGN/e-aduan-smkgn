# e-Aduan SMKGN — Siap untuk diterbitkan

Aplikasi web statik dengan Supabase sebenar untuk SMK Guar Nangka.

## Sudah disediakan
- URL Supabase dan publishable key (bukan secret) dalam `config.js`
- Login guru dan penyelaras menggunakan Supabase Auth
- Guru melihat aduan sendiri; penyelaras melihat semua aduan dan boleh menukar status
- Borang aduan dengan gambar, dashboard, carian, sejarah tindakan dan eksport CSV
- Logo sekolah, reka bentuk responsif biru/kuning

## Cara terbitkan
1. Ekstrak ZIP. Pastikan fail `index.html`, `app.js`, `config.js`, `style.css` dan folder `assets` berada dalam direktori utama laman.
2. Muat naik direktori ke static hosting HTTPS seperti Vercel, Netlify atau Cloudflare Pages. Tetapan framework: Other / static; build command: kosong; output directory: `.`
3. Buka URL laman dan login menggunakan akaun Supabase Authentication yang sudah didaftarkan.
4. Untuk menambah guru, gunakan Supabase Dashboard > Authentication > Users > Add user.
5. Semak tetapan Authentication > URL Configuration / email jika menggunakan e-mel pemulihan kata laluan.

## Nota keselamatan
- Jangan letak secret key atau service_role key dalam frontend.
- Data dihadkan oleh Row Level Security (RLS).
- Gambar dalam private bucket `aduan-images`.
- Matikan public sign-up di Supabase Auth jika akaun hanya boleh dibuat oleh pentadbir.
- Uji dua akaun berasingan sebelum penggunaan rasmi.
- Fail `schema.sql` lama hanyalah rujukan; JANGAN jalankan semula kerana migrasi database sudah dilaksanakan.

**Status:** database disambungkan, kod siap untuk hosting, tetapi URL awam belum diterbitkan dan ujian login end-to-end belum dilaksanakan.
