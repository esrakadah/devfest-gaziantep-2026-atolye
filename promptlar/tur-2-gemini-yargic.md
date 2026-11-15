# Tur 2 (15 dakika): İmza tatlın ve Gemini yargıç

Aynı projede, AI Studio sohbetine şunu yapıştır. Tatlı adını ve şaka malzemesini kendine göre değiştirebilirsin.

```text
Oyunumuza iki şey ekle:

1. KENDİ İMZA TATLIM VE ŞAKA MALZEMEM:
Kodla çizilmiş, renkli inline SVG (viewBox="0 0 120 120") iki yeni ürün ekle:
- İmza tatlı: "Fıstıklı Katmer Sarma" (Tatlı rafına)
- Şaka malzemesi: "İsot Biberi" (Şekerin hemen yanına)
Bunları açıp kapatan bir "Özel Menü" düğmesi ekle.

2. GEMINI MÜŞTERİ YARGICI:
"Siparişi Servis Et!" basılınca gemini-3.5-flash-lite modelini bir kez çağır ve cevabı şu JSON şemasıyla iste:
{
  "ratingStars": sayı (1-5),
  "tasteVerdict": "sweet_perfection" | "salty_sabotage" | "spicy_chaos" | "incomplete_tray",
  "customerFace": "happy" | "shocked" | "salty_disgusted",
  "headline": metin,
  "customerReaction": metin (Türkçe, Gaziantep'e özgü esprili bir yorum)
}
Model sadece yorumu ve şakayı yazsın. YILDIZI KOD VERSİN:
- Tepside tuz, acı sos ya da isot biberi varsa: 1 yıldız, üzgün müşteri.
- Şaka yok ama içecek, tatlı ya da şeker eksikse: 3 yıldız.
- Hepsi var, şaka yok: 5 yıldız, mutlu müşteri.
Model farklı yıldız söylerse kodun kuralı geçerli olsun.

3. YEDEK PLAN:
Gemini 8 saniyede cevap vermezse ya da hata dönerse oyun donmasın: hazır, esprili Türkçe yedek cevaplardan birini göster.
```

**Kontrol et (üç soru):**

1. Cevap her seferinde aynı alanlarla geliyor mu?
2. İnterneti kapatınca (ya da DevTools'ta "Offline") oyun donuyor mu, yedek cevap mı geliyor?
3. Tuz varken model "5 yıldız" dese bile ekranda 1 yıldız mı görünüyor?

Sonraki: [Tur 3](tur-3-yayinla.md)
