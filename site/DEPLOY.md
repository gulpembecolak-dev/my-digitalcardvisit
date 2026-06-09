# Pem Colak — dijital kartvizit · Vercel deploy

Domain hedefi: **https://my-digitalcardvisit.vercel.app/**

## İçindekiler
- `index.html` — kırmızı versiyon (kartın kendisi)
- `pem.vcf`   — rehbere eklenecek kişi (opsiyonel; sayfa zaten kendi içinde de üretiyor)
- `preview.png` — WhatsApp önizleme görseli (1200×630) — **SEN eklemelisin**

## Aşama 1 — preview.png oluştur (WhatsApp kartı için şart)
1. `index.html`'i tarayıcıda aç, kart açıldıktan sonra ekran görüntüsü al.
2. 1200×630 px boyutuna getir (Önizleme/Preview app ile crop+resize).
3. `site/preview.png` olarak kaydet. (Görsel olmazsa WhatsApp sadece başlığı gösterir.)

## Aşama 2 — Vercel'e deploy (CLI)
Terminalde:
```
npm i -g vercel        # bir kez
cd "site"
vercel login           # tarayıcıdan giriş
vercel                  # ilk deploy — proje adı sorulunca: my-digitalcardvisit
vercel --prod           # production yayını
```
Çıkan URL `my-digitalcardvisit.vercel.app` değilse: index.html içindeki 3 adet
`https://my-digitalcardvisit.vercel.app` satırını gerçek URL ile değiştir, tekrar `vercel --prod`.

## Aşama 3 — WhatsApp testi
1. Linki bir sohbete yapıştır → önizleme kartı çıkmalı.
2. Eski/yanlış görünüyorsa: https://developers.facebook.com/tools/debug → URL gir → "Scrape Again".
   (WhatsApp bu cache'i kullanır.)
