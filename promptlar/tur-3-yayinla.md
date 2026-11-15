# Tur 3 (10 dakika): Yayınla ve sahneye gel

Tur 2'yi bitiremediysen sorun yok: Tur 1 uygulaman da yayınlanır.

## Seçenek A: Cloud Run'a yayınla (kredi kartı yok)

> Ücretsiz yayın (Starter Tier) sadece uygun kişisel Gmail hesaplarında çıkar. Okul ya da iş hesabında, daha önce ücretli Cloud hesabı olanlarda ve bazen yeni açılmış hesaplarda çıkmaz; en fazla 2 uygulama yayınlanır. Çıkmazsa Seçenek B'ye geç. Kaynak: [Starter Tier](https://cloud.google.com/blog/topics/developers-practitioners/the-starter-tier-for-google-ai-studio-explained), [AI Studio'dan yayınlama](https://aistudio.google.com/docs/aistudio-deploying).

1. Sağ üstte **Publish**'e bas. Çıkan ekranlarda sırayla **Get started**, projeni onayla ve **Continue**, **Continue with free URL**, en sonda **Publish your app** de (bazı adımlar çıkmayabilir). Uygulaman Cloud Run'da açılır; adres `.run.app` ya da `.ai.studio` ile bitebilir, ikisi de doğru. Gemini anahtarın sunucuda kalır, tarayıcıya gömülmez.
2. İstersen sağ üstten **Sync to GitHub** ile kodu kendi GitHub hesabına gönder.

## Seçenek B: Paylaşım linki (kurulum yok)

Sağ üstte **Share**, sonra linki herkese açık yap ve **Default to fullscreen** seç. Dikkat: linki açanların Gemini istekleri senin kotandan düşer, sadece güvendiğin kişilerle paylaş.

## Sahneye gel

Linki telefonundan aç, baristana bir kahve sor, zamanlayıcıyı başlat ve elini kaldır: sonda en fazla dört kişiyi 60 saniyelik demo için sahneye davet ediyoruz.

Sosyal medyada paylaşırsan **#DevFest** etiketini kullan.

## İleri seviye: Esra'nın Flutter oyununu Cloud Run'a

Sahnedeki örnek kafe (Tatlı mı Tuzlu mu?) bir Flutter uygulaması. Merak edersen kendi Cloud projende yayınlayabilirsin.

> Bu yol faturalandırması açık bir Google Cloud projesi ister (Cloud Run ve Secret Manager). Yoksa Yol A'yı kullan.

[Ana repo](https://github.com/esrakadah/devfest-2026-backyard-barista-cloudrun) içindeki `flutter_client` klasöründen:

```bash
flutter analyze && flutter test
```

Gemini anahtarını bir kez Secret Manager'a koy (web build'e hiç girmez):

```bash
printf '%s' "$GEMINI_API_KEY" | gcloud secrets create gemini-api-key --data-file=-
```

```bash
gcloud secrets add-iam-policy-binding gemini-api-key --member="serviceAccount:$(gcloud projects describe "$(gcloud config get-value project)" --format='value(projectNumber)')-compute@developer.gserviceaccount.com" --role=roles/secretmanager.secretAccessor
```

Yayınla:

```bash
gcloud run deploy backyard-barista --source . --region europe-west3 --allow-unauthenticated --set-secrets GEMINI_API_KEY=gemini-api-key:latest --max-instances 3
```

Dockerfile'daki nginx oyunu sunar ve `/api/gemini/generate` isteğini anahtarı sunucuda ekleyerek Gemini'ye iletir. Secret yoksa oyun hazır cevaplarla çalışır.
