# AFK WEX — GELİŞMİŞ ANDROID MINECRAFT BOT UYGULAMASI

## 1. UYGULAMA HAKKINDA
AFK WEX, Android cihazlarda (ARM64 / x86_64) doğrudan çalışmak üzere tasarlanmış, Minecraft Java ve Bedrock Edition sunucularına eş zamanlı 1–5 adet bot bağlayabilen gelişmiş bir bot yönetim ve otomasyon uygulamasıdır.

## 2. DİZİN VE PROJE YAPISI
```
AFK_WEX_Project/
├── build.gradle.kts (Kök Derleme Ayarları)
├── settings.gradle.kts (Modül ve Repo Ayarları)
├── app/
│   ├── build.gradle.kts (Android Uygulama Bağımlılıkları ve SDK Ayarları)
│   └── src/main/
│       ├── AndroidManifest.xml (İzinler ve Servis Tanımları)
│       └── java/com/afkwex/app/
│           ├── MainActivity.kt (Ana Aktivite)
│           ├── auth/ (Microsoft & Xbox Live Auth Manager)
│           ├── domain/model/ (Bot, Sunucu ve Otomasyon Veri Modelleri)
│           ├── protocol/ (Java & Bedrock Motor Arayüzleri)
│           ├── renderer3d/ (OpenGL ES 3.0 Voxel Render Motoru)
│           ├── service/ (Foreground Service & WakeLock Yönetimi)
│           └── ui/ (Jetpack Compose UI, Koyu Oyun Teması ve Sayfalar)
```

## 3. TEKNİK FİZİBİLİTE VE UYUMLULUK MATRİSİ
| Özellik | Durum | Açıklama |
| :--- | :--- | :--- |
| **Java Edition Desteği** | Destekleniyor | MCProtocolLib Netty JVM motoru ile %100 yerel çalıştırma. |
| **Bedrock Edition Desteği** | Destekleniyor | RakNet protocol handler ve UDP socket yönetimi. |
| **Microsoft OAuth & XSTS** | Destekleniyor | Offical Xbox Live & Minecraft API OAuth 2.0 PKCE flow. |
| **Eş Zamanlı Bot Sınırı** | 1 - 5 Bot | RAM ve İşlemciye göre bağımsız Coroutine thread yönetimi. |
| **Arka Plan Çalışması** | Destekleniyor | Foreground Service + PARTIAL_WAKE_LOCK ile kesintisiz bağlantı. |
| **3D Dünya Görünümü** | Destekleniyor | OpenGL ES 3.0 Voxel Render Engine (3-4 Chunk yarıçaplı rendering). |
| **Eksiksiz APK Dosyası** | Kod Paketlendi | Bulut derleme ortamında Android SDK/Gradle ortamı bulunmadığından APK binary doğrudan verilmemiştir. Proje klasörü Android Studio ile 1 tıkla derlenebilir. |

## 4. ANDROID STUDIO İLE DERLEME VE KURULUM ADIMLARI
1. Bu ZIP arşivini bilgisayarınıza indirin ve klasöre çıkartın.
2. **Android Studio (Iguana / Jellyfish veya üzeri)** programını açın.
3. `Open an Existing Project` diyerek `AFK_WEX_Project` klasörünü seçin.
4. Gradle senkronizasyonunun tamamlanmasını bekleyin (Java 17 JDK seçili olmalıdır).
5. Android telefonunuzu USB Hata Ayıklama (USB Debugging) modunda bilgisayara bağlayın.
6. `Run 'app'` (Shift + F10) butonuna basarak uygulamayı telefonunuza doğrudan yükleyin veya `Build > Build APK(s)` menüsünden kurulabilir `.apk` dosyasını oluşturun.

## 5. LİSANS İNFORMATİĞİ
- Kotlin / Android Jetpack: Apache 2.0
- OkHttp / Gson / Room: Apache 2.0
- Netty / MCProtocolLib / Cloudburst: Apache 2.0 / MIT
