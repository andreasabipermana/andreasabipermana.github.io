---
title: "Catatan - Import Berkas CSV dengan Mysqlimport"
date: 2022-10-02T18:19:48+07:00
hiddenFromHomePage: true
comment:
  enable: false
tags: ["Mysql", "Import"]
categories: ["notes"]
---

Pada catatan singkat ini saya akan menulis mengenai cara melakukan import berkas CSV ke database dengan aplikasi Mysqlimport.

## Apa itu Mysqlimport ?
Mysqlimport merupakan aplikasi di sisi client dari mysql yang menyediakan perintah untuk melakukan LOAD DATA SQL.

## Perintah
Berikut ini syntax perintah dari Mysqlimport  
```bash
mysqlimport [options] db_name textfile1 [textfile2 ...]
```
{{< admonition note "Catatan" >}}
Untuk setiap berkas teks yang diberi nama pada baris perintah, mysqlimport menghapus ekstensi apa pun dari nama berkas dan menggunakan hasilnya untuk menentukan nama tabel tempat mengimpor konten file.
{{< /admonition >}}

## Perintah Import CSV
Berikut ini perintah untuk melakukan import CSV
```bash
mysqlimport --ignore-lines=1 \
            --fields-terminated-by=, \
            --local -u nama_user \
            -ppassworddb nama_database \
             nama_tabel.csv
```
{{< admonition note "Catatan" >}}
Perintah diatas akan melakukan import berkas nama_tabel.csv dengan beberapa konfigurasi yaitu `--ignore-lines` untuk mengabaikan baris ke n, konfigurasi `--fields-terminated-by=` untuk menentukan delimiter dari CSV, dan terakhir `--local` untuk membaca berkas input secara lokal dari host klien.
{{< /admonition >}}
Apabila berkas CSV menggunakan delimiter `;` maka perintahnya kan menjadi seperti dibawah
```bash
mysqlimport --ignore-lines=1 \
            --fields-terminated-by=';' \
            --local -u nama_user \
            -ppassworddb nama_database \
             nama_tabel.csv
```
{{< admonition note "Catatan" >}}
Perintah diatas kurang lebih sama seperti perintah sebelumnya, hanya saja menggunakan delimiter yang berbeda dan pada konfigurasi menggunakan single quote `';'` karena akan terjadi error apabila langsung menentukan `;` sebagai delimiter.
{{< /admonition >}}

## Sumber
* Dokumentasi Resmi Mysqlimport : [https://dev.mysql.com/doc/refman/8.0/en/mysqlimport.html](https://dev.mysql.com/doc/refman/8.0/en/mysqlimport.html)
