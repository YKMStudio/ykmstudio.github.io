# Özet: 5 oyun, site ve App Store Connect (19 Ekim 2026)

Bu dosya sitede yayınlanmaz (`_config.yml` içinde hariç tutuldu).

## 1. ATT (takip izni)

- Yalnızca **Block Streak** "Allow Tracking" soruyordu. Kaldırıldı: izin penceresi, ilgili iOS kodu ve Info.plist'teki `NSUserTrackingUsageDescription` artık yok. Reklamlar reklam kimliği (IDFA) olmadan geliyor.
- Diğer dört oyunda ATT zaten yoktu; build adımları açıklama satırını siliyor. **Hiçbir oyun takip yapmıyor.**

## 2. Game Center

- Yalnızca **Block Streak** kullanıyordu; App Store Connect'te liderlik tablosu ve başarım hiç tanımlanmamıştı (oyundaki butonlar boş ekran açardı, red riski).
- Bu tür bir oyun için şart olmadığından **tamamen kaldırıldı**: liderlik tablosu ve başarım butonları, Game Center kodu ve izni. Beş sürümde de Game Center kapalı.

## 3. Diller

App Store sayfaları 8 dilde (en, tr, pt-BR, es-MX, id, ms, vi, th). Oyun içi eksikler tamamlandı:

| Oyun | Önce | Şimdi |
|---|---|---|
| Block Streak | 5 dil | 8 dil (Endonezce, Malayca, Vietnamca eklendi) |
| Arrow Shift | 6 dil | 8 dil (Malayca, Vietnamca eklendi) |
| Color Sort, Flow Dots, Dunk Wings | 8 dil | değişmedi |

Vietnamca harfler için Kanit yazı tipi kullanılıyor (ücretsiz, OFL lisansı).

## 4. Yeni build'ler (hepsi App Store Connect'te 1.0 sürümüne bağlandı)

| Oyun | Build | Değişiklik |
|---|---|---|
| Block Streak | 2610191010 | ATT ve Game Center yok, 8 dil |
| Arrow Shift | 2610191014 | Sürüm 0.1.0 → 1.0.0, 8 dil |
| Color Sort | 2610191021 | Yalnızca iPhone |
| Dunk Wings | 2610191027 | Yalnızca iPhone |
| Flow Dots | 2610191033 | Yalnızca iPhone |

Color Sort, Dunk Wings ve Flow Dots iPad'i de destekliyordu ama iPad ekran görüntüsü yoktu; App Store bu yüzden gönderimi kabul etmezdi. Artık yalnızca iPhone (iPad'de iPhone modunda çalışır).

## 5. App Store Connect'te yapılanlar

| Alan | Ne yapıldı |
|---|---|
| App Privacy | Beş oyunda da aynı beyan yayınlandı: Device ID, Product Interaction, Advertising Data, Coarse Location, Crash Data, Performance Data; hepsi "kimliğe bağlı değil", **takip yok**. (Dunk Wings'te hiç beyan yoktu; Arrow Shift ve Block Streak yarımdı.) |
| Support / Marketing URL | Color Sort ve Flow Dots'ta 7'şer dilde, Block Streak'te Türkçede `wewosoft.com` adresleri vardı (403 veriyordu). Hepsi `ykmstudio.github.io/<oyun>/` yapıldı. |
| Privacy Policy URL | Color Sort ve Flow Dots'ta 7'şer dilde, Block Streak'te Türkçede boştu. Dolduruldu (Türkçe → KVKK sayfası). |
| İnceleme iletişim bilgisi | Dunk Wings ve Arrow Shift'te boştu; diğer oyunlardaki bilgilerinle dolduruldu. |
| Copyright | Dunk Wings'te boştu: "2026 Mehmet Sönmez (YKM Studio)". |
| İnceleme notları | Dunk Wings'e not eklendi; Block Streak'in notu ATT'siz hâle göre güncellendi. |
| App Accessibility | Beşi için beyan taslağı kaydedildi (Color Sort ve Flow Dots: renge bağlı olmayan ayrım; Arrow Shift: azaltılmış hareket; diğerleri: listelenen özellik yok). Apple bunu ancak uygulama yayındayken yayınlamaya izin veriyor; yayından sonra "App Accessibility" sayfasından **Publish** ile yayınla. Gönderim için zorunlu değil. |
| Fiyat / ülkeler | Beşi de ücretsiz, 173 ülke. |
| Ekran görüntüleri | Beşinde de 8 dilde iPhone görüntüleri var. |

Dokunulmayan alanlar: açıklama, anahtar kelimeler, tanıtım metni, uygulama adları ve alt başlıklar, kategori, yaş sınırı (hepsi 4+).

## 6. Site (ykmstudio.github.io)

- Block Streak'in gizlilik sayfaları ATT ve Game Center olmadan güncellendi; destek sayfasından Game Center sözleri çıkarıldı.
- Tüm yasal sayfalar oyunların App Store adlarını kullanıyor.
- `APP_STORE_CONNECT.md` "hiçbir oyun takip yapmıyor" durumuna göre güncellendi.

## 7. Senin yapman gerekenler

1. **Push et:** site ve beş oyun reposu (her birinde push edilmemiş commit'ler var).
2. **TestFlight'ta dene:** dil seçimi (özellikle Vietnamca ve Tayca), ayarlardaki linkler, "Diğer Oyunlar" butonu; Block Streak açılışta takip izni sormamalı.
3. Her oyunda **Add for Review → Submit for Review**. Apple eksik bir şey görürse o ekranda listeler.
4. Yayından sonra her oyunda **App Accessibility → Publish**.

Dikkat: Color Sort'un Türkçe mağaza adında yazım hatası var ("Mercan Resıfı" → "Mercan Resifi" olmalı). Doldurulmuş alanlara dokunmadığım için değiştirmedim.
