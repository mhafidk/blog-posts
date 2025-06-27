---
title: YAGNI Principle - Yang Perlu Perlu Aja!
date: 2025-04-12
image: /blog-images/yagni-principle.webp
slug: yagni-principle-yang-perlu-perlu-aja
tags:
  - programming
---

## Apa Itu YAGNI?

Kemarin kita udah bahas prinsip KISS dan DRY, sekarang giliran YAGNI. YAGNI singkatan dari _You Ain’t Gonna Need It_—prinsip yang bilang: jangan bikin sesuatu yang belum tentu dibutuhkan. Tapi apa udah benar benar paham tentang YAGNI dan bisa diimplementasiin saat ngoding? Untuk bisa lebih paham tentang YAGNI, coba lihat analogi dibawah ini.

Bayangin kamu disuruh ibu mu ke warung untuk beli beras, telur, dan cabe ijo. Saat sampai di warung, kamu punya inisiatif untuk beli minyak goreng, garam, dan sayur. Setelah kamu beli itu semua, dengan perasaan senang kamu pulang ke rumah. Sampai di rumah, ibu mu marah marah, "Kenapa kamu beli minyak goreng, garam, dan sayur? Kan kita ga perlu minyak goreng, garam, dan sayur. Jadi lebih mahal juga kan, kembaliannya jadi sedikit!". Kamu hanya diam, menunduk, dan berpikir kalau aja tadi aku ga beli minyak goreng, garam, dan sayur.

Dalam konteks programming, prinsip YAGNI menekankan untuk hanya mengerjakan fitur yang benar-benar dibutuhkan—bukan yang _mungkin_ dibutuhkan nanti. Pada analogi diatas, requirement yang dibutuhkan hanya beras, telur, dan cabe ijo aja, jadi tidak perlu membeli minyak goreng, garam, dan sayur.

## Kenapa YAGNI Itu Penting?

Beberapa alasan kenapa prinsip YAGNI ini penting dalam proses software development yaitu,

- **Lebih hemat waktu dan tenaga**. Waktu dan tenaga adalah sumber daya yang penting, sayang kalau dihabiskan untuk mendevelop sesuatu yang diluar requirements, yang mana belum pasti akan digunakan.
- **Mengurangi potensi _bug_**. Semakin banyak code yang ditulis, semakin banyak kemungkinan bug yang terjadi.
- **Mengurangi _technical debt_**. Setiap baris code yang ditulis adalah tanggung jawab di masa depan (perlu di*maintain*).

## Contoh Penerapan YAGNI

Pak Boss: "Tolong buatkan aplikasi blog ya, requirementnya satu post hanya dibuat oleh satu penulis."

Kamu (Developer): "Oke pak"

**Tidak YAGNI** 👎

Kamu berpikir

> Hmm... kayaknya keren juga nih kalau satu post bisa dikerjain sama beberapa penulis, mungkin nanti aplikasinya akan support itu.

Mulai lah kamu nulis code nya.

```ruby
# posts table
t.references :authors

# models
class Post < ApplicationRecord
  has_and_belongs_to_many :authors
end

class Author < ApplicationRecord
  has_and_belongs_to_many :posts
end
```

Jadilah kamu buat table posts yang support beberapa penulis, design user interface yang bisa memilih beberapa penulis, meskipun saat ini rencananya satu post hanya bisa dibuat oleh satu penulis dan ga ada rencana untuk support penulisan oleh beberapa penulis dalam waktu dekat.

**YAGNI** 👍

Kamu berpikir

> Oke, aplikasi blog, satu post ditulis oleh satu penulis.

Mulai lah kamu nulis masterpiece.

```ruby
# posts table
t.references :author

# models
class Post < ApplicationRecord
  belongs_to :author
end
```

Saat nulis code masterpiece mu itu, di dalam benak mu udah tertanam, satu post satu author, jadi kamu hanya membuat asosiasi one-on-one antara post dan author. Kamu bisa menyelesaikan aplikasinya dengan cepat, mengurangi potensi bug karena code yang kamu tulis sedikit, code yang kamu tulis pun simple dan `clean`, dan boss pun senang.

Gimana kalau di masa depan ada kebutuhan untuk mensupport satu post ditulis oleh beberapa penulis? Biarkan dirimu dimasa depan yang menangani itu :)

## Akhir Kata

Dengan menerapkan prinsip YAGNI ini, tidak hanya code mu yang semakin sehat, tapi dirimu sebagai developer juga ikut sehat! Dengan memfokuskan untuk mendevelop feature yang dibutuhkan saat ini saja akan lebih menghemat waktu, tenaga, mengurangi _technical debt_, dan mengurangi potensi _bug_ yang dapat terjadi.

Lebih baik kamu matangkan planning terlebih dulu sebelum memulai menulis code dan pastikan seluruh requirement yang dibutuhkan.

> Jangan ngoding buat masa depan yang belum tentu datang. Fokus ke hari ini—itu baru YAGNI.😎
