# mekaxstudio.github.io

Mekax Studio web sitesi: https://mekaxstudio.github.io

GitHub Pages bu repoyu Jekyll ile kendisi derler; ayrı bir build adımı yok, `main`'e push etmek yeterli.

## Yapı

| Adres | Dosya |
|---|---|
| `/` | `index.html` |
| `/games/`, `/about/`, `/contact/` | `games/`, `about/`, `contact/` |
| `/<oyun>/` (destek + tanıtım, App Store "Support URL") | `<oyun>/index.html` |
| `/<oyun>/privacy.html` (App Store "Privacy Policy URL") | `<oyun>/privacy.html` |
| `/<oyun>/privacy-tr.html` (KVKK aydınlatma metni) | `<oyun>/privacy-tr.html` |
| `/<oyun>/terms.html` | `<oyun>/terms.html` |
| `/app-ads.txt` (AdMob, tüm oyunlar için tek dosya) | `app-ads.txt` |

Oyunlar: `blockstreak`, `colorsort`, `flowdots`, `dunkwings`, `arrowshift`, `farmmow`.

- Ortak üst menü ve alt bilgi: `_layouts/default.html`; oyun sayfalarındaki ikon ve sekmeler: `_layouts/game.html`.
- Oyun listesi (ad, tür, kısa açıklama, e-posta, App Store linki): `_data/games.yml`. Ana sayfa, Games, Contact ve alt bilgi buradan beslenir.
- İkonlar: `assets/icons/<oyun>.png` (256x256).

## Yeni oyun eklemek

1. `_data/games.yml`'a bir kayıt ekle.
2. `assets/icons/<slug>.png` koy.
3. Mevcut bir oyunun klasörünü kopyala (`<slug>/index.html`, `privacy.html`, `privacy-tr.html`, `terms.html`), front matter'daki `game:` alanını ve metinleri yeni oyuna göre düzenle. Gizlilik metni oyunun gerçekten kullandığı SDK'lara (reklam, analiz, bildirim, ATT…) uymalı.

## Yerelde önizleme

```
gem install --user-install jekyll webrick
$(ruby -e 'puts Gem.user_dir')/bin/jekyll serve
```
