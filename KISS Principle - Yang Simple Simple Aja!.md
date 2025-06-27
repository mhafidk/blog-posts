---
title: KISS Principle - Yang Simpel Simpel Aja!
date: 2025-04-12
image: /blog-images/kiss-principle.webp
slug: kiss-principle-yang-simpel-simpel-aja
tags:
  - programming
---

## Apa Itu KISS?

Keep It Simple, Stupid atau KISS adalah satu dari prinsip-prinsip pemrograman penting yang harus dipahami oleh seorang software developer apapun rolenya. Tapi apa sih KISS itu? Coba lihat contoh di bawah ini,

Ada orang yang bertanya tentang arah ke cafe A ke seorang bapak bapak, bapak bapak itu menjawab,

> Oh cafe A, tau mas, masnya tinggal lurus aja sampai ada rumah yang ada pohon mangga nya belok kanan, masnya muter dulu 3 kali, terus lurus lagi sampai mencium aroma-aroma kopi dan ada bapak bapak lagi minum kopi, jangan lupa disapa, setelah itu belok kiri, ada tempat yang banyak mobil dan motor nya, halamannya luas, ada tukang parkirnya, nah itu cafe A

Baru jalan sebentar udah lupa arahannya tadi, orang itu nanya lagi ke bapak bapak lain, bapak bapak itu menjawab,

> Oh cafe A, langganan saya itu mas, masnya tinggal lurus aja, sampai pertigaan ke kanan, masih lurus lagi, mentok belok kiri, nanti ada tulisannya Cafe A, nah itu mas

Gimana? Paham?

KISS atau Keep It Simple, Stupid adalah prinsip untuk membuat sesuatu sesimpel mungkin. Dalam programming, dapat diartikan dengan menulis code sesimpel mungkin sehingga code tersebut dapat dengan mudah dipahami.

## Kenapa KISS Penting?

Kenapa menulis code yang sederhana dan simpel itu penting? Karena,

- Lebih mudah **dimaintain**. Code yang simpel dan sederhana lebih mudah untuk dipahami, dimengerti, didebug kalau ada bug, dan direfactor.
- Lebih mudah **dipahami** rekan tim. Developer lain bisa dengan mudah memahami code kita.
- Lebih **sedikit** kemungkinan bug. Semakin simpel dan sederhana code nya, maka semakin sedikit potensi bug nya.

## Contoh Penerapan KISS

Misalkan kita mau mengecek apakah user seorang admin atau bukan.

**Tidak KISS** 👎

```ruby
def user_admin?(user)
   user.roles.map(&:name).include?(‘administrator’) ||
   user.name.include?(‘admin’) ||
   user.id == user.team.user_id ||
   pengecekan_user_lainnya(user)
end
```

**KISS** 👍

```ruby
def admin?(user)
   user.has_role?(‘admin’)
end
```

Lebih simple contoh yang kedua kan? Bayangin kalau misalkan kamu developer baru yang melihat code di contoh pertama, pasti akan kebingunan, kenapa harus ngecek nama user ada admin nya atau engga, kenapa harus ngecek user_id dari team nya?

Dengan menerapkan KISS, bukan berarti kita harus seluruhnya menjadi lebih simpel dan sederhana. Kalau memang sebuah masalah itu kompleks dan kita sudah berusaha menyederhanakannya sesederhana mungkin, it’s okay.

## Akhir Kata

Prinsip KISS bukan berarti "menyederhanakan secara sembrono", tapi membuat sesuatu **sesederhana yang tetap masuk akal dan mudah dipahami**. Terdengar mudah untuk dilakukan, tapi pada aplikasinya kadang kita masih mengabaikan prinsip ini, butuh waktu dan ribuan baris code untuk bisa membuat diri kita aware dan terbiasa terhadap prinsip KISS.

Untuk bisa menerapkan prinsip KISS ini, cobalah bertanya diakhir code yang kita tulis

> **Udah simpel belum ya?**
