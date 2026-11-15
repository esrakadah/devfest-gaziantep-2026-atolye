# Tur 1 (10 dakika): Kafe tezgahı

Aşağıdaki kutunun tamamını kopyala, [Google AI Studio](https://aistudio.google.com) **Build** moduna yapıştır ve gönder.

```text
"Tatlı mı Tuzlu mu?" adında, iki kişilik, hiç yazı yazmadan oynanan eğlenceli bir web oyunu yap. Arayüz Türkçe olsun.

1. KAFE: Üst barda "DevFest Gaziantep · Şehitkamil Baklava & Kahve Evi" yazsın.

2. TEZGAH VE TEPSİ: Oyuncular sadece dokunarak 3 gözlü bir tahta tepsiyi doldurur (her raftan 1 ürün):
- Göz 1, İçecek (1 tane seç): Espresso, Süt, Menengiç Kahvesi
- Göz 2, Tatlı (1 tane seç): Kruvasan, San Sebastian Cheesecake, Fıstıklı Baklava
- Göz 3, Kavanozlar (1 tane seç, yan yana ve birbirine benzer dursun, hangisinin şaka olduğu belli olmasın):
  - Şeker (tatlı, 5 yıldız için gerekli)
  - Tuz (ŞAKA malzemesi, rafta şekerle aynı görünür)
  - Acı Sos (ŞAKA malzemesi)

3. GÖRSELLER: Ürün resimlerini şu adresten yükle:
https://raw.githubusercontent.com/esrakadah/devfest-2026-backyard-barista-cloudrun/main/flutter_client/assets/base/{kategori}/{dosya}.png
Dosyalar: drinks/espresso.png, drinks/milk.png, drinks/menengic_coffee.png, foods/croissant.png, foods/san_sebastian.png, foods/baklava.png, toppings_pranks/sugar_jar.png, toppings_pranks/salt_shaker.png, toppings_pranks/chili_sauce.png, customers/customer_happy.png, customers/customer_shocked.png, customers/customer_salty_disgusted.png
Resim yüklenmezse her ürün için renkli bir inline SVG göster, oyun internetsiz de çalışsın.

4. İKİ OYUNCU: Oyuncu 1 ("Barista") içecekleri seçer, Oyuncu 2 ("Pastacı") tatlı ve kavanozu seçer. Tepside küçük bir "🤫" rozeti olsun ama rafta kırmızı uyarı olmasın. Büyük bir "Siparişi Servis Et!" düğmesi ekle.

5. ŞİMDİLİK BASİT PUAN: Servis edilince: tuz ya da acı sos varsa 1 yıldız ve üzgün müşteri, 3 göz dolu ve şeker varsa 5 yıldız ve mutlu müşteri, eksik varsa 3 yıldız. Skoru üstte göster.
```

**Kontrol et:** Oyun açıldı mı? Baklava + kahve + şeker 5 yıldız, tuz 1 yıldız veriyor mu? Vermiyorsa AI Studio'ya ne gördüğünü yaz: "Tuz koyunca 5 yıldız veriyor, düzelt."

Sonraki: [Tur 2](tur-2-gemini-yargic.md)
