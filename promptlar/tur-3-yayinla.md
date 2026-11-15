# Tur 3 (10 dakika): Yayınla ve sahneye gel

## Yol A: AI Studio'dan (kredi kartı yok)

> Ücretsiz yayın (Starter Tier) kişisel Google hesapları içindir. Okul, iş ya da daha önce ücretli Cloud hesabı olan hesaplarda çıkmayabilir; en fazla 2 uygulama yayınlanır. Kaynak: [Starter Tier](https://cloud.google.com/blog/topics/developers-practitioners/the-starter-tier-for-google-ai-studio-explained), [AI Studio'dan yayınlama](https://aistudio.google.com/docs/aistudio-deploying).

1. Sağ üstte **Publish**, sonra **Get started** ve **Publish your app**. Uygulaman Cloud Run'da `https://...run.app` adresinde açılır. Gemini anahtarın sunucuda kalır, tarayıcıya gömülmez.
2. İstersen sağ üstten **Sync to GitHub** ile kodu kendi GitHub hesabına gönder.
3. `.run.app` linkini telefonundan aç, tatlıya tuz at, 1 yıldızı gör ve elini kaldır: sahnede 60 saniyelik demo ve ödül seni bekliyor. 🏆

Publish çıkmıyorsa: [örnek kafeyi](https://backyard-barista-389486729482.europe-west3.run.app/?remote_city=gaziantep) ve arkadaşlarının kafelerini test et (Yol C).

## Yol B: Flutter projesini Cloud Run'a

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
