---
title: DRY Principle - Satu Untuk Semua!
date: 2025-04-12
image: /blog-images/dry-principle.png
slug: dry-principle-satu-untuk-semua
tags:
  - programming
---

## Apa Itu DRY?

Don't Repeat Yourself atau DRY mungkin bagi kalian yang sudah berada di dunia ngoding, udah ga asing lagi sama istilah DRY tersebut. Tapi sebenarnya, apa sih DRY itu? Aku coba pakai analogi untuk menjelaskan DRY.

Bayangin kamu lagi masak, dan setiap kali kamu mau buat bumbu, kamu selalu ngulek ulang lagi bumbu itu dari nol, padalah resep nya sama. Capek kan pasti harus selalu buat bumbu yang sama terus-terusan, meskipun prosesnya sama. Nah, DRY hadir supaya kamu ga perlu lagi terus-terusan ngulang proses yang sama.

Dalam konteks coding, prinsip DRY berarti menghindari pengulangan kode atau logika yang sama.

## Kenapa DRY Itu Penting?

Apakah prinsip DRY itu penting? Penting! Kenapa bisa penting?

- **Lebih memudahkan me*maintain* code**. Bayangin kalau kamu punya banyak function untuk menghitung sebuah perhitungan di banyak tempat, terus ada adjustment di perhitungannya, good luck ngeganti semua functionnya.
- **Mengurangi bug**. Pengulangan bisa bikin kamu lupa memperbarui semua bagian yang terdampak.
- **Lebih _clean_ dan efisien**. Code yang ga berulang-ulang lebih enak dilihat, mudah dipahami, dan enak dimaintain.
  Jadi DRY bukan hanya sekedar style dalam ngoding, tapi juga investasi jangka panjang untuk kesehatan code mu dan mengurangi pr mu di masa depan.

## Contoh Penerapan DRY

Mari lihat contoh penerapan DRY. Contoh ini ku tulis pakai Ruby, tapi bisa juga dipakai dengan bahasa pemrograman lainnya.

**Tidak DRY** 👎

```ruby
def print_invoice
  puts "Company Name"
  puts "Address Line 1"
  puts "Address Line 2"
end

def print_receipt
  puts "Company Name"
  puts "Address Line 1"
  puts "Address Line 2"
end
```

Bisa dilihat pada 2 function diatas, `print_invoice` dan `print_receipt` memiliki isi yang sama, sama-sama ngeprint company name dan address. Gimana kalau seandainya kamu perlu nambahin nomor telpon perusahaan? Harus ditambahin satu satu kan. Coba kamu lihat contoh penerapan DRY dibawah ini

**DRY** 👍

```ruby
def print_company_info
  puts "Company Name"
  puts "Address Line 1"
  puts "Address Line 2"
end

def print_invoice
  print_company_info
end

def print_receipt
  print_company_info
end
```

Dengan DRY lebih simpel kan? Kalau ada penambahan nomor telpon perusahaan, kamu hanya perlu merubah 1 function aja yaitu `print_company_info`.

## Akhir Kata

Kesimpulannya dengan menerapkan DRY pada code, kita dapat membuat code kita lebih `clean`, efisien, mudah dipahami, dan mudah di*maintain* dengan cara mengurangi code yang memiliki fungsi yang sama.

Tapi... kita ga harus kaku kaku banget, ada sedikit pengulangan lebih baik daripada harus membuat abstraksi yang terlalu rumit. Terapkan DRY ini dengan bijak, dan pr mu di masa depan akan berkurang.
