---
title: "Menjalankan CTFd Menggunakan Docker Compose"
date: 2022-09-30T19:42:11+07:00
---

Pada postingan blog pertama ini saya akan membagikan bagaimana cara menjalankan CTFd dengan menggunakan Docker Compose.

## Apa itu CTFd
CTFd adalah kerangka kerja Capture The Flag yang berfokus pada kemudahan penggunaan dan kemampuan penyesuaian. CTFd memiliki fitur yang cukup lengkap untuk menjalankan acara lomba  Capture The Flag. CTFd ini mudah digunakan dan tersedia juga berbagai macam plugin dan tema, sehingga sangat mudah untuk di kustomisasi CTFd dibuat dalam bentuk aplikasi Web. Berikut ini tampilan dari CTFd.

## Fitur CTFd
* Buat tantangan, kategori, petunjuk, dan tanda Anda sendiri dari Antarmuka Admin
* Tantangan Penilaian Dinamis
* Membuat tantangan kustom Anda sendiri
* Unggah file ke server atau backend yang kompatibel dengan Amazon S3
* Perlindungan bruteforce otomatis
* Kompetisi berbasis individu dan tim
* Sembunyikan Skor dari publik
* Bekukan Skor pada waktu tertentu
* Dukungan email SMTP + Mailgun
* Dukungan konfirmasi email
* Dukungan lupa kata sandi
* Mengimpor dan Mengekspor data CTF untuk arsip
* Dan lain lain

Lebih lengkapnya anda bisa melihat di dokumentasi resmi CTFd pada tautan berikut.

## Persiapan
Siapkan beberapa bagian berikut sebelum menjalankan CTFd menggunakan Docker Compose
* Sediakan 1 VPS dengan Sistem Operasi Ubuntu/Debian
* Pastikan Docker Engine dan Docker Compose telah terinstall di VPS
