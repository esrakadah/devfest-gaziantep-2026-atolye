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
"Siparişi Servis Et!" basılınca gemini-3.5-flash-lite modelini bir kez çağır. Modele tepsideki ürünleri ve kodun verdiği yıldızı gönder, cevabı şu JSON şemasıyla iste:
{
  "headline": metin,
  "customerReaction": metin (Türkçe, Gaziantep'e özgü esprili bir müşteri yorumu)
}
Model sadece başlığı ve yorumu yazsın. Yıldızı, sonucu ve müşteri yüzünü KOD belirlesin:
- Tepside tuz, acı sos ya da isot biberi varsa: 1 yıldız, üzgün müşteri.
- Şaka yok ama içecek, tatlı ya da şeker eksikse: 3 yıldız.
- Hepsi var, şaka yok: 5 yıldız, mutlu müşteri.

3. YEDEK PLAN:
Gemini 8 saniyede cevap vermezse ya da hata dönerse oyun donmasın: hazır, esprili Türkçe yedek cevaplardan birini göster.
```

**Kontrol et (üç soru):**

1. Cevap her seferinde aynı iki alanla (headline, customerReaction) geliyor mu?
2. İnterneti kapatınca (ya da DevTools'ta "Offline") oyun donuyor mu, yedek cevap mı geliyor?
3. Tuzlu tepsi her seferinde 1 yıldız alıyor mu? Yıldızı kodun verdiğini kodda gör.

Sonraki: [Tur 3](tur-3-yayinla.md)
