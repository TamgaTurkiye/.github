# Katkı Rehberi (Ortak — Tüm Tamga Repoları İçin Geçerli)

Bu dosya, Tamga organizasyonundaki tüm repolar için varsayılan katkı kuralıdır. Bir repo kendi `CONTRIBUTING.md` dosyasını tanımlamışsa, o dosya bu kurallara ek bilgi sağlar, çelişmez.

## Temel Akış

```
Issue açılır (görev/öneri tanımlanır)
    ↓
İlgilenen kişi assign edilir ("claimed" etiketi)
    ↓
Kişi fork + branch + içerik üretir
    ↓
Pull Request açılır (ilgili issue'ya referans verir)
    ↓
Maintainer review eder, gerekirse değişiklik ister
    ↓
Onaylanırsa merge edilir, issue otomatik kapanır
```

Hiçbir dış katkıcıya doğrudan yazma (push) yetkisi verilmez. `main` branch korumalıdır; her değişiklik PR üzerinden geçer ve maintainer onayı gerektirir.

## Katkıcı Güven Kademeleri (Trust Tiers)

| Kademe | Kim açabilir | Hangi içerik türü |
|---|---|---|
| **Tier 1** | Herkes, ilk PR'dan itibaren | checklist, defensive-lesson, davranış kalıbı/tespit notu (aktör adı geçmeyen) |
| **Tier 2** | En az 2 onaylanmış PR geçmişi | sector-risk-note, threat-trend-report, malware-family-profile (attribution-sensitive olmayan) |
| **Tier 3** | En az 5 onaylanmış PR veya maintainer onayı | incident-brief, attribution-sensitive her şey (motivasyon/aktör iddiası içeren içerik) |
| **maintainer** | Sadece repo sahibi/onaylı maintainer | Temel metodoloji dosyaları |

Bu kademelendirme keyfi bir engel değil, editöryal sorumluluktur: yüksek riskli içerik türleri (özellikle attribution/motivasyon içerenler), katkı geçmişi olan kişilerce yazıldığında hata oranı düşer.

## Wave Sistemi

Her repo, içeriğini tek seferde değil aşamalı olarak açar:

- **Wave 1:** Tier 1 issue'lar + maintainer-written metodoloji dosyaları (repo açıldığında hazır)
- **Wave 2:** Tier 2 issue'lar (Wave 1'den en az bir PR merge olduktan sonra açılır)
- **Wave 3:** Tier 3 / attribution-sensitive issue'lar (Wave 2'den en az iki katkıcı Tier 2'ye ulaştıktan sonra açılır)

## Issue Seçme ve Üstlenme

1. Açık issue'lardan birini seç (etiketlere bakarak kendi seviyene uygun olanı bul: `good-first-issue`, `help-wanted`).
2. Issue'ya yorum yazıp kendini assign etmeyi iste veya maintainer'dan assignment iste.
3. 14 gün içinde PR açılmazsa issue tekrar açık hale gelebilir, başka biri üstlenebilir.

## PR Açarken

- `PULL_REQUEST_TEMPLATE.md` doldurulmadan PR review'a alınmaz.
- Her kaynak için `source_url` ve mümkünse `archived_url` (Wayback Machine veya archive.today) eklenmelidir.
- Tek kaynaklı iddialar düşük güven (`low confidence`) kabul edilir.
- İçerik türüne uygun Safety Checklist tamamlanmalıdır (bkz. `methodology/`).
- Contributor Rights / No Ownership Claim onay kutusu işaretlenmelidir (bkz. `methodology/contributor-rights.md`).

## Araştırma Metodolojisi

Her katkı, `methodology/` klasöründeki üç temel kurala uyar:

- **Verified Facts vs Analyst Assessment** ayrımı — bkz. `methodology/facts-vs-assessment.md`
- **Kaynak güvenilirliği ve arşivleme** — bkz. `methodology/source-reliability.md`
- **Güvenli dil ilkeleri** — bkz. `methodology/safe-language-guidelines.md`

## Credit

Her katkı, PR'da contributor olarak görünür ve ilgili reponun README'sindeki Contributors bölümüne eklenir. Katkı haklarının kapsamı için `methodology/contributor-rights.md`'ye bakın.
