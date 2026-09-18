# Build APK Final

## Cara otomatis (disarankan)
1. Upload seluruh folder project ini ke repository GitHub.
2. Push ke branch `main`.
3. Buka tab **Actions**.
4. Jalankan workflow **Build BasketCoach AI APK**.
5. Setelah selesai, buka hasil workflow dan download artifact `basketcoach-ai-release`.
6. Di dalam artifact terdapat `app-release.apk`.

Workflow otomatis akan:
- memasang Flutter stable,
- membuat project Android,
- mengambil dependencies,
- menjalankan `flutter build apk --release`,
- menyimpan APK sebagai artifact.

## Backend production
Flutter app sudah diarahkan ke:
https://cijldixlozgifuepcstj.supabase.co/functions/v1/basketcoach-ai

Edge Function memerlukan `OPENAI_API_KEY` sebagai secret server untuk AI generatif penuh.
Jangan memasukkan service-role key atau OpenAI API key ke source Flutter.

## Local build
Pada komputer yang sudah memasang Flutter + Android SDK:
flutter pub get
flutter create --platforms=android --org com.basketcoachai .
flutter build apk --release

APK:
build/app/outputs/flutter-apk/app-release.apk
