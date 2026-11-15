# DevFest Gaziantep 2026 Atölyesi: Tatlı mı Tuzlu mu? ☕🥐🧂

**Konuşma:** Shipping Flutter + Gemini to Production with Firebase AI Logic: Real Numbers and Live Coding

**Konuşmacı:** Esra Kadah (Flutter & Dart GDE, Antigua Mobile) · 15 Kasım 2026, 15:00 - 16:30

Bugün iki oyunculu küçük bir kafe oyunu kuruyoruz. Tepsiye içecek, tatlı ve şeker koyuyorsun, Gemini müşteri olup yorum yazıyor. Şekerin yanında bir **tuz** var: tatlıya tuz atarsan müşteri bunu yakalıyor ve 1 yıldız veriyor.

> Kodu artık AI da yazıyor. Sizin işiniz geleni kontrol etmek.

## Önce oyna (30 saniye)

👉 **[Örnek kafeyi aç (Gaziantep)](https://backyard-barista-389486729482.europe-west3.run.app/?remote_city=gaziantep)**

Baklava + kahve + şeker koy: 5 yıldız. Şimdi şekerin yerine tuz koy: 1 yıldız. İşte bunu kuruyoruz.

## Yolunu seç

- **A: Tarayıcı** (çoğunuz): bilgisayar ve kişisel Gmail hesabı. Google AI Studio'ya prompt yapıştırıp oyunu kurup yayınlıyorsun.
- **B: Flutter**: Flutter kurulu bilgisayar. Hazır Flutter projesini çalıştırıp değiştiriyorsun.
- **C: Telefon**: sadece telefon. Örnek kafeyi ve arkadaşlarının kafelerini test ediyorsun.

## Yol A: Tarayıcıda, kurulum yok

1. [aistudio.google.com](https://aistudio.google.com) adresini aç, **kişisel Gmail** hesabınla gir (okul ya da iş hesabında ücretsiz yayın çıkmayabilir).
2. Soldan **Build** modunu seç.
3. **Tur 1 (10 dk):** [`promptlar/tur-1-kafe.md`](promptlar/tur-1-kafe.md) içindeki prompt'u kopyala, yapıştır, gönder. Oyun açılınca dene.
4. **Tur 2 (15 dk):** [`promptlar/tur-2-gemini-yargic.md`](promptlar/tur-2-gemini-yargic.md) ile kendi imza tatlını ve Gemini yargıcını ekle.
5. **Tur 3 (10 dk):** [`promptlar/tur-3-yayinla.md`](promptlar/tur-3-yayinla.md) ile **Publish** de, `.run.app` linkini telefonundan aç.

Bir şey bozulursa panik yok: prompt'u yeniden yapıştır ya da AI Studio'ya "bu hatayı düzelt" yaz.

### Her turdan sonra üç soru

AI kodu yazdı, kontrol sende:

1. **Cevap şemaya uyuyor mu?** Gemini her seferinde aynı alanları (yıldız, yorum) döndürüyor mu?
2. **İnternet giderse ne oluyor?** Oyun donuyor mu, yedek cevap mı veriyor?
3. **Puanı kim veriyor?** Tuz varken model 5 yıldız dese bile ekranda 1 yıldız görünüyor mu?

## Yol B: Flutter

Hazır proje ana repoda: [esrakadah/devfest-2026-backyard-barista-cloudrun](https://github.com/esrakadah/devfest-2026-backyard-barista-cloudrun)

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

Ücretsiz Gemini anahtarı: [aistudio.google.com/apikey](https://aistudio.google.com/apikey). Anahtarla:

```bash
flutter run -d chrome --dart-define=DEFAULT_CITY=gaziantep --dart-define=GEMINI_API_KEY=ANAHTARIN
```

Sonra Antigravity ya da sevdiğin AI asistanına projeyi göster, kendi tatlını ve şaka malzemeni ekletip Gemini yargıcını dene (fikir için Tur 2'ye bak). Cloud Run'a yayın komutları: [`promptlar/tur-3-yayinla.md`](promptlar/tur-3-yayinla.md), Yol B bölümü.

## Sahne ve ödül 🏆

Oyununu yayınlayıp sahnede **60 saniyede** gösteren ilk dört kafeye Google renkli piksel gözlük ve Dash hediyeleri. Tatlıya tuz atıp 1 yıldızlı yorumu canlı göster, yeter.

## Bugünden dört şey

1. Cevabı şemayla isteyin.
2. Her AI çağrısına zaman aşımı ve yedek plan koyun.
3. Anahtar ve kota kişiye özel olsun, anahtar tarayıcıya gömülmesin.
4. Şakayı model yazsın, puanı kodunuz versin.

## Slaytlar

- [Konuşma slaytları](https://esrakadah.github.io/devfest-gaziantep-2026-atolye/slaytlar/konusma/)
- [Atölye slaytları](https://esrakadah.github.io/devfest-gaziantep-2026-atolye/slaytlar/atolye/)

Bilgisayarda ok tuşlarıyla gezinilir.

## Daha fazlası

- Kaynak kod, makale ve İngilizce prompt'lar: [ana repo](https://github.com/esrakadah/devfest-2026-backyard-barista-cloudrun)
- Firebase AI Logic: [firebase.google.com/docs/ai-logic](https://firebase.google.com/docs/ai-logic)
- Esra: [esratech.com](https://esratech.com)

Bu repo Google'ın resmi materyali değildir; DevFest Gaziantep atölyesi için hazırlandı. Lisans: MIT.
