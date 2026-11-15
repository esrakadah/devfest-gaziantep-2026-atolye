# DevFest Gaziantep 2026 Atölyesi: Backyard Barista (Türkçe) ☕

**Konuşma:** Shipping Flutter + Gemini to Production with Firebase AI Logic: Real Numbers and Live Coding

**Konuşmacı:** Esra Kadah (Flutter & Dart GDE, Antigua Mobile) · 15 Kasım 2026, 15:00 - 16:30

Bugün Google AI Studio'da kendi kahve uygulamanı kuruyorsun. Gemini senin baristan: tat tercihlerine göre çekirdek, kavrum, süt ve tarif öneriyor. Sonra demleme zamanlayıcısı ve alışveriş listesi ekliyorsun, en sonda uygulamanı yayınlıyorsun.

> Kodu artık AI da yazıyor. Senin işin geleni kontrol etmek.

Bu atölye, Google'ın resmi DevFest 2026 Vibe Lounge rehberi "The Backyard Barista"dan Türkçe olarak uyarlandı. Rehberin aslı İngilizce: [Backyard Barista (Google)](https://docs.google.com/document/d/12Vvc5VPJkHvRzgMgcHdvMFDzxsWtfBZzzoo0Y9HM_8M/edit?tab=t.0).

## Önce örnek kafeyi gör (30 saniye)

Konuşmada gösterdiğim Flutter oyunu: 👉 **[Örnek kafeyi aç](https://backyard-barista-389486729482.europe-west3.run.app/?remote_city=gaziantep)**

Baklava + kahve + şeker koy: 5 yıldız. Şekerin yerine tuz koy: Gemini yakalar, 1 yıldız. Bugün sen de AI'lı bir kafe uygulaması kuracaksın, ama kendi baristanla.

## Yolunu seç

- **A: Tarayıcı** (çoğunuz): bilgisayar ve kişisel Gmail hesabı. AI Studio'ya prompt yapıştırıp uygulamayı kurup yayınlıyorsun.
- **B: Flutter** (ileri seviye): Flutter kurulu bilgisayar. Örnek kafenin Flutter projesini çalıştırıp inceliyorsun.
- **C: Telefon**: sadece telefon ya da Gmail yok. Örnek kafeyi oyna, sonra yanındaki bir bilgisayarın başına geç ve prompt'ları onunla birlikte yapıştır.

## Yol A: Tarayıcıda, kurulum yok

1. [ai.studio/build](https://ai.studio/build) adresini aç, **kişisel Gmail** hesabınla gir (okul, iş ya da daha önce ücretli Cloud hesabı olan hesaplarda ücretsiz yayın çıkmayabilir).
2. **Tur 1 (10 dk):** [`promptlar/tur-1-barista.md`](promptlar/tur-1-barista.md): baristanı kur, bir kahve iste.
3. **Tur 2 (15 dk):** [`promptlar/tur-2-demleme-ve-liste.md`](promptlar/tur-2-demleme-ve-liste.md): demleme zamanlayıcısı ve alışveriş listesi ekle.
4. **Tur 3 (10 dk):** [`promptlar/tur-3-yayinla.md`](promptlar/tur-3-yayinla.md): **Publish** ya da **Share**, linki telefonundan aç.

Her özelliği ekledikten sonra dene, sonra bir sonrakine geç. Bir şey bozulursa panik yok: AI Studio'ya "bu hatayı düzelt" yaz ya da prompt'u yeni bir sohbette yeniden yapıştır. Geride kaldıysan bir tur atla, Tur 3'te yine bizimlesin.

Wi-Fi çekmezse telefonunun hotspot'unu aç ya da yanındakinin ekranında birlikte devam et. Gemini "kota" ya da 429 hatası verirse 30 saniye bekleyip tekrar dene.

### Her turdan sonra kontrol et

Konuşmadaki ilk soru "AI cevabına nasıl güveniyoruz?" idi. Uygulamanda onu üç yerden sor:

1. **Cevap hep aynı düzende mi?** Tarif kartı her seferinde aynı alanlarla mı geliyor?
2. **İnternet giderse ne oluyor?** Uygulama donuyor mu, anlaşılır bir hata mı gösteriyor?
3. **Kim hesaplıyor?** Öneriyi model yazsın, zamanlayıcıyı ve listeyi kod hesaplasın.

## Yol B: Flutter (ileri seviye)

Örnek kafenin kodu: [esrakadah/devfest-2026-backyard-barista-cloudrun](https://github.com/esrakadah/devfest-2026-backyard-barista-cloudrun)

```bash
git clone https://github.com/esrakadah/devfest-2026-backyard-barista-cloudrun.git
```

```bash
cd devfest-2026-backyard-barista-cloudrun/flutter_client && flutter pub get
```

Anahtarın yoksa da çalışır (hazır cevaplarla):

```bash
flutter run -d chrome --dart-define=DEFAULT_CITY=gaziantep --dart-define=OFFLINE_MODE=true
```

Ücretsiz Gemini anahtarı: [aistudio.google.com/apikey](https://aistudio.google.com/apikey). Anahtarla (sadece kendi bilgisayarında dene, anahtar derlenen uygulamaya girer; yayınlarken [Tur 3](promptlar/tur-3-yayinla.md)'teki Secret Manager yolunu kullan):

```bash
flutter run -d chrome --dart-define=DEFAULT_CITY=gaziantep --dart-define=GEMINI_API_KEY=ANAHTARIN
```

## Sahne

Sonda en fazla dört kişiyi 60 saniyelik demo için sahneye davet ediyoruz: linkini aç, baristana bir kahve sor, göster.

## Bugünden dört şey

1. Cevabı şemayla iste: düz metin değil, hep aynı alanlar.
2. Her AI çağrısına zaman aşımı ve yedek plan koy.
3. Anahtar ve kota kişiye özel olsun, anahtar tarayıcıya gömülmesin.
4. Öneriyi model yazsın, kararı kodun versin.

## Slaytlar

- [Atölye slaytları](https://esrakadah.github.io/devfest-gaziantep-2026-atolye/slaytlar/atolye/)

Bilgisayarda ok tuşlarıyla gezinilir.

## Daha fazlası

- Google'ın resmi rehberi (İngilizce): [The Backyard Barista](https://docs.google.com/document/d/12Vvc5VPJkHvRzgMgcHdvMFDzxsWtfBZzzoo0Y9HM_8M/edit?tab=t.0)
- Örnek kafenin kaynak kodu ve makalesi: [ana repo](https://github.com/esrakadah/devfest-2026-backyard-barista-cloudrun)
- Firebase AI Logic: [firebase.google.com/docs/ai-logic](https://firebase.google.com/docs/ai-logic)
- Esra: [esratech.com](https://esratech.com)

Bu repo Google'ın resmi materyali değildir; DevFest Gaziantep atölyesi için Google'ın rehberinden Türkçeye uyarlandı. Repo içeriğinin lisansı: MIT.
