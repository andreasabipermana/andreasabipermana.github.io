---
title: "Catatan - Perintah Merubah Nama Pengguna Linux"
date: 2022-10-28T09:11:00+07:00
hiddenFromHomePage: true
comment:
  enable: false
tags: ["Linux", "Username"]
categories: ["notes"]
---

Pada catatan singkat ini saya akan menulis mengenai cara merubah nama pengguna atau Username di Linux beserta Home direktorinya. Perintah yang digunakan adalah `usermod` dan `groupmod`.


## Apa itu Usermod dan Groupmod
Usermod merupakan perintah pada linux yang digunakan untuk melakukan modifikasi akun user. Sementara Groupmod merupakan perintah pada linux yang digunakan untuk melakukan modifikasi definisi group pada sistem linux.

## Skenario
Disini saya memiliki user bernama coba akan saya ganti menjadi abipermana.

## Perintah 1: Usermod
Berikut ini perintah Usermod untuk melakukan perubahan nama login dan home direktori dari user.  
```bash 
usermod --login user_baru --move-home --home home_direktori_baru user_lama
 ```
{{< admonition note "Catatan" >}}
Perintah diatas akan melakukan perubahan informasi user dengan beberapa konfigurasi yaitu `--login` untuk melakukan perubahan nama login pengguna `--move-home=` untuk melakukan pemindahan data dari home direktory `--home` untuk menentukan home direktory untuk user baru.
{{< /admonition >}}

Berdasarkan perintah diatas maka perintah yang dijalankan pada skenario diatas  
```bash 
usermod --login abipermana --move-home --home /home/abipermana coba 
```
## Perintah 2: Groupmod
Berikut ini perintah Groupmod untuk melakukan perubahan group dari user yang telah diubah.  
```bash
groupmod --new-name user_baru user_lama 
```
{{< admonition note "Catatan" >}}
Perintah diatas akan melakukan perubahan informasi nama group dengan konfigurasi yaitu `--new-name` untuk menentukan nama group baru.
{{< /admonition >}}

Berdasarkan perintah diatas maka perintah yang dijalankan pada skenario diatas  
```bash 
groupmod --new-name abipermana coba 
```

## Sumber
* Serverfult : [https://serverfault.com/questions/437342/how-can-i-rename-a-unix-user](https://serverfault.com/questions/437342/how-can-i-rename-a-unix-user)  
* Manual usermod : ```bash man usermod```  
* Manual groupmod : ```bash man group```   
