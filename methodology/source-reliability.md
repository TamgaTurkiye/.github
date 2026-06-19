# Kaynak Güvenilirliği Modeli

## Üç Katmanlı Değerlendirme

Tamga, ham bir iddiayı yayınlanabilir bilgiye dönüştürürken üç aşamalı bir süzgeç kullanır:

```
Sinyal → İstihbarat → Kanıt
```

- **Sinyal:** Forum, sosyal medya veya tek bir habercide görülen, henüz doğrulanmamış iddia. Tek başına yayınlanmaz.
- **İstihbarat:** Birden fazla kaynakla bağlamlandırılmış, güven seviyesi atanmış bilgi. Analyst Assessment'a girebilir.
- **Kanıt:** Resmî açıklama, teknik analiz veya çok kaynaklı doğrulanmış IOC/olay raporuyla desteklenen bilgi. Verified Facts'e girebilir.

## Admiralty Scale (Ağır İçerik Türleri İçin Zorunlu)

İncident-brief, threat-trend-report ve attribution-sensitive içeriklerde, NATO kökenli ve tehdit istihbaratı camiasında (MISP, SANS, CTI pratiği) standart olarak kullanılan Admiralty Scale uygulanır.

**Kaynak Güvenilirliği (A–F):**

| Kod | Anlamı |
|---|---|
| A | Tamamen güvenilir — sürekli doğru bilgi geçmişi |
| B | Genellikle güvenilir — ara sıra hata |
| C | Orta düzeyde güvenilir — karışık geçmiş |
| D | Genellikle güvenilir değil |
| E | Güvenilmez |
| F | Yargılanamaz |

**Bilgi Güvenilirliği (1–6):**

| Kod | Anlamı |
|---|---|
| 1 | Doğrulanmış — başka kaynaklarla teyit edilmiş |
| 2 | Muhtemelen doğru |
| 3 | Mümkün |
| 4 | Şüpheli |
| 5 | Muhtemel değil |
| 6 | Yargılanamaz |

İkisi birleştirilip kombine kod olarak yazılır: örneğin **B2** (genellikle güvenilir kaynak, muhtemelen doğru bilgi).

## Zorunlu Metadata Alanları (Ağır Katman)

```yaml
source_reliability: "B"
information_reliability: "2"
confidence_code: "B2"
estimative_probability: "likely"
independent_sources_count: 3
archived_sources_count: 2
```

## Arşivleme Zorunluluğu

Her kaynak linki için mümkünse bir arşiv kopyası (Wayback Machine veya archive.today) de eklenir. Bunun iki nedeni var: haberler/bloglar zamanla kaldırılır veya düzenlenir (link rot), ve arşiv damgası "bu kaynak yazıldığı tarihte gerçekten bunu söylüyordu" kanıtı sağlar.

PR template'inde her kaynak için `source_url` + `archived_url` ikilisi istenir.

## Bağımsız Kaynak Sayısı Kuralı

- Tek kaynaklı iddia → otomatik `low confidence`
- 2 bağımsız kaynak → `medium confidence` olabilir
- 3+ bağımsız ve çelişmeyen kaynak → `high confidence` olabilir

Bu kural özellikle motivasyon/attribution iddiaları için istisnasızdır — tek kaynaklı bir attribution iddiası hiçbir koşulda Verified Facts'e giremez.

## Orta Katman (Sector-Risk-Note, attribution-sensitive olmayan)

Bu içerik türlerinde tam Admiralty kodu zorunlu değildir; sözel ölçek (Yüksek / Orta / Düşük) yeterlidir. Yine de en az 2 bağımsız kaynak şartı geçerlidir.
