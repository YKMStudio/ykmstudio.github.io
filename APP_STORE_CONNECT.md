# App Store Connect: nereye ne yazılacak (tüm oyunlar)

_18 Ekim 2026. Bu dosya sitede yayınlanmaz (`_config.yml` içinde hariç tutuldu)._

Aşağıdaki her adres https://mekaxstudio.github.io üzerinde gerçek bir sayfa açar. Her yerde iletişim adresi: **mekaxstudio@gmail.com**.

## 1. Oyun başına adresler

| Oyun | Bundle ID | Privacy Policy URL | Support URL | Marketing URL |
|---|---|---|---|---|
| Block Streak | com.ykmstudio.blockstreak | https://mekaxstudio.github.io/blockstreak/privacy.html | https://mekaxstudio.github.io/blockstreak/ | https://mekaxstudio.github.io/blockstreak/ |
| Color Sort | com.ykmstudio.colorsort | https://mekaxstudio.github.io/colorsort/privacy.html | https://mekaxstudio.github.io/colorsort/ | https://mekaxstudio.github.io/colorsort/ |
| Flow Dots | com.ykmstudio.flowdots | https://mekaxstudio.github.io/flowdots/privacy.html | https://mekaxstudio.github.io/flowdots/ | https://mekaxstudio.github.io/flowdots/ |
| Dunk Wings | com.ykmstudio.dunkwings | https://mekaxstudio.github.io/dunkwings/privacy.html | https://mekaxstudio.github.io/dunkwings/ | https://mekaxstudio.github.io/dunkwings/ |
| Meow Arrows (eski: Arrow Shift) | com.ykmstudio.arrowshift | https://mekaxstudio.github.io/arrowshift/privacy.html | https://mekaxstudio.github.io/arrowshift/ | https://mekaxstudio.github.io/arrowshift/ |

App Store Connect'te alanların yeri:

- **Privacy Policy URL:** Uygulama → *App Privacy* → Privacy Policy → Edit. İstendiği zaman değiştirilebilir, yeni build gerekmez.
- **Support URL** ve **Marketing URL:** Uygulama → sürüm sayfası (ör. *1.0 Prepare for Submission*) → *Support URL* / *Marketing URL*. Başka diller eklediysen her dilde ayrıca doldurulmalı.
- **Copyright:** `2026 Mekax Studio`.
- **License Agreement (EULA):** Apple'ın standart sözleşmesinde kalsın. Oyunlarda abonelik olmadığı için App Store açıklamasına ayrıca link eklemek gerekmez. Bizim kullanım şartlarımız (`.../terms.html`) her oyunun ayarlarından açılıyor ve Apple'ın standart sözleşmesine atıf yapıyor.

Marketing URL neden önemli: AdMob, `app-ads.txt` dosyasını App Store sayfasında görünen geliştirici web sitesinin alan adında arar. Marketing / Support URL `mekaxstudio.github.io` olunca AdMob https://mekaxstudio.github.io/app-ads.txt dosyasını bulur. Bu dosya beş oyunun hepsini kapsar (yayıncı `pub-6657137577216041`). Oyun yayına çıktıktan bir gün kadar sonra AdMob → Apps → app-ads.txt ekranında "Verified" görünür.

## 2. App Privacy cevapları

**"Yes, we collect data from this app"** seç, sonra aşağıdaki veri türlerini işaretle. Hepsinde **Linked to the user's identity = No**.

### Beş oyun (ATT'siz AdMob + Firebase Analytics; Block Streak hariç hepsinde Crashlytics)

| Veri türü | Amaçlar | Takip için kullanılıyor mu |
|---|---|---|
| Identifiers → Device ID | Third-Party Advertising, Analytics | No |
| Usage Data → Product Interaction | Analytics, Third-Party Advertising | No |
| Usage Data → Advertising Data | Third-Party Advertising | No |
| Location → Coarse Location | Third-Party Advertising | No |
| Diagnostics → Crash Data | App Functionality, Analytics | No |
| Diagnostics → Performance Data | Third-Party Advertising | No |

Hiçbir oyun "Allow Tracking" (ATT) penceresini göstermiyor ve reklam kimliğini okumuyor. Bu yüzden "Do you or your third-party partners use data for tracking?" sorusunun cevabı **No**. Info.plist dosyasında `NSUserTrackingUsageDescription` olmamalı; beş oyunun iOS build adımı bunu siliyor. Block Streak'te Crash Data işaretlenmez (Crashlytics yok), ama AdMob'un Performance Data'sı yine işaretlenir.

Göndermeden önce Google'ın güncel listeleriyle karşılaştır: https://developers.google.com/admob/ios/privacy/data-disclosure ve https://firebase.google.com/docs/ios/app-store-data-collection

## 3. Yaş sınırı ve diğer sorular

- Age rating anketi: her şey **None / No** → 4+. Reklamlar yaş sınırını değiştirmez. "Made for Kids" **seçilmemeli** (oyunlar normal AdMob reklamı gösteriyor).
- Content Rights: "does not contain, show, or access third-party content".
- Export compliance: Info.plist'te zaten cevaplı (`ITSAppUsesNonExemptEncryption = NO`).
- İnceleme için giriş gerekiyor mu: **No**.

## 4. Oyunlarda neler değişti (her oyun için yeni build gerekir)

Beş oyunun ayarlarında artık şunlar var: Gizlilik Politikası (Türkçe oyuncular KVKK sayfasını görür), Kullanım Şartları, Bize Ulaşın (e-posta), Gizlilik Seçenekleri (yalnızca Google'ın onay formunun yasal olarak gerektiği yerlerde, ör. AB/İngiltere) ve **Diğer Oyunlar (More Games)**. Diğer Oyunlar, App Store uygulamasında geliştirici sayfasını açar (`itms-apps://apps.apple.com/developer/id1839694002`). Bu buton her oyunun ana ekranında da var.

| Oyun | Değişiklikler |
|---|---|
| Block Streak | Linkler mekaxstudio.github.io'ya taşındı (eski ykmstudioofficial.github.io sayfaları 404 veriyordu). More menüsüne Bize Ulaşın, Gizlilik Seçenekleri ve Diğer Oyunlar eklendi; ana ekrana Diğer Oyunlar butonu eklendi. Yeni Firebase projesi `block-streak-a9069`. |
| Color Sort | Linkler mekaxstudio.github.io'ya taşındı. Ana ekrana Diğer Oyunlar butonu eklendi. Yeni Firebase projesi `color-sort-29b88`. |
| Flow Dots | Linkler mekaxstudio.github.io'ya taşındı. Ana ekranda Ayarlar'ın yanına Diğer Oyunlar eklendi. Yeni Firebase projesi `flow-dots-f50f0`. |
| Dunk Wings | Linkler mekaxstudio.github.io'ya taşındı (eski dunkwings-support sitesi hiç kurulmamıştı). Ana ekrana Diğer Oyunlar butonu eklendi. Firebase dosyası zaten güncelmiş. |
| Arrow Shift | Firebase Analytics + Crashlytics eklendi (`arrow-shift-590ad`); Google Mobile Ads da diğer oyunlar gibi Swift Package Manager'a geçti. Ayarlar'a Diğer Oyunlar, Gizlilik Politikası, Kullanım Şartları, Bize Ulaşın ve Gizlilik Seçenekleri eklendi; ana ekranda Ayarlar'ın yanına Diğer Oyunlar eklendi. Ana ekrandaki "Prototype · codename" yazısı kaldırıldı (App Review'a bitmemiş uygulama izlenimi verirdi). |

Geliştirici sayfası, aynı Apple geliştirici hesabıyla (MEHMET SONMEZ, id 1839694002) yayınlanan tüm oyunları gösterir. Bir oyun yayına çıkınca orada görünür.

## 5. "Submit for Review"a basmadan önce

- [ ] Yukarıdaki üç adres telefondaki Safari'de açılıyor.
- [ ] Oyunda: Ayarlar → Gizlilik Politikası / Kullanım Şartları / Bize Ulaşın / Diğer Oyunlar doğru yeri açıyor.
- [ ] App Privacy cevapları 2. bölümle aynı.
- [ ] TestFlight build'inden gelen olaylar Firebase → Analytics → DebugView'da görünüyor (Xcode'da `-FIRDebugEnabled` ekle).
