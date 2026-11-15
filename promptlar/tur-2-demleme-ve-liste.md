# Tur 2 (15 dakika): Demleme zamanlayıcısı ve alışveriş listesi

Her özelliği ayrı ayrı ekle ve bir sonrakine geçmeden dene. Bir şey bozulursa AI Studio'ya ne gördüğünü yaz: "Zamanlayıcı sıfırda durmuyor, düzelt."

Tur 1 uygulaman çalışmıyorsa önce Tur 1 prompt'unu yeni bir sohbette yeniden yapıştır, sonra buraya dön.

## 1. Demleme zamanlayıcısı

```text
Tarif kartına "Demlemeyi Başlat" düğmesi ekle. Basınca tarifteki adımlara göre görsel bir geri sayım başlasın (örneğin önce 30 saniye ön demleme, sonra ana döküm). O an hangi adımda olunduğu ve kalan süre büyük yazsın. Sıfıra gelince kısa bir "Kahven hazır" mesajı çıksın.
```

## 2. Alışveriş listesi

```text
Tarif kartına "Alışveriş Listesi" düğmesi ekle. Basınca tarif için gereken çekirdek, süt ve ekipmanları kopyalamaya hazır, madde madde bir liste olarak göster ve "Kopyala" düğmesi koy.
```

## Bonus (zaman kalırsa)

**Tarifi paylaş:**

```text
"Tarifi Kopyala" düğmesi ekle: tarifi emojili, arkadaşa gönderilecek kısa bir metin olarak panoya kopyalasın.
```

**Tarif defteri (Firebase):** AI Studio'da **Add Firebase and auth** kartını kullan, sonra şunu yaz:

```text
Kullanıcı Google ile giriş yapabilsin ve beğendiği tarifleri "Tarif Defterim" listesine kaydedebilsin. Tekrar giriş yapınca kayıtlı tarifler yine görünsün.
```

Firebase ile dışarıda veri saklamak bazı hesaplarda ücretli plan isteyebilir; çıkmazsa atla.

**Kontrol et:**

1. Zamanlayıcı tarifteki adımlarla aynı mı, yoksa uyduruyor mu?
2. İnterneti 10 saniye kapatıp tarif iste: uygulama donuyor mu, anlaşılır bir hata mı gösteriyor?
3. Listeyi ve süreleri kim hesaplıyor, kod mu model mi? AI Studio'ya sor. Model öneri yazsın, sayan ve hesaplayan kod olsun.

Sonraki: [Tur 3](tur-3-yayinla.md)
