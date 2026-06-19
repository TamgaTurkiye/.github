# Verified Facts vs Analyst Assessment Guide

## Amaç

Bu rehber, Tamga içeriğinde "doğrulanmış olgu" ile "analist yorumu/değerlendirmesi" arasındaki farkı tanımlar. Bu ayrım, Tamga'nın temel güvenilirlik vaadinin (her içerik kaynaklı olacak) teknik olarak uygulanmasıdır. Bu dosya, incident-brief, threat-trend-report ve attribution-sensitive içeriklerde zorunludur; checklist ve defensive-lesson türlerinde isteğe bağlıdır.

## Tanımlar

**Verified Fact:** Birden fazla bağımsız, güvenilir kaynakla doğrulanmış, tartışmasız gözlem. ("X şirketi, Y tarihinde Z türünde bir olay bildirdiğini açıkladı.")

**Analyst Assessment:** Doğrulanmış olgulardan çıkarılan, ama kendisi doğrulanmış olgu olmayan yorum, çıkarım veya tahmin. ("Bu davranış, X motivasyonuna işaret edebilir.") Bu bölüm her zaman olasılık dili (estimative language) ile yazılır ve katkı sağlayan kişinin adıyla credit'lenir.

## Neden Ayrılır?

Üç olgu/yorum cümlesi birbirine karıştığında, okuyucu hangi kısmın kanıta dayandığını hangi kısmın yorum olduğunu ayırt edemez. Bu hem güvenilirlik kaybına hem de hukuki riske (özellikle attribution iddialarında) yol açar.

## Worked Examples

**Örnek 1 — Yanlış (olgu ve yorum karışık):**
> "Şirket X'e yapılan saldırı, muhtemelen finansal motivasyonlu bir grup tarafından gerçekleştirildi ve veri sızıntısı yaşandı."

**Örnek 1 — Doğru (ayrılmış):**
> **Verified Facts:** Şirket X, [kaynak] tarafından bildirilen bir veri sızıntısı olayını doğruladı.
> **Analyst Assessment:** Açık kaynak raporlarındaki davranış kalıbı, finansal motivasyonla *roughly even chance* (orta olasılık) örtüşüyor; kesin bir motivasyon tespiti yapılamaz.

**Örnek 2 — Yanlış:**
> "Bu saldırıyı devlet destekli bir grup yaptı."

**Örnek 2 — Doğru:**
> **Verified Facts:** [Kaynak A] ve [Kaynak B], bu kampanyayı belirli bir tehdit kümesiyle ilişkilendirdi.
> **Analyst Assessment:** Attribution: *publicly reported*, ancak bağımsız teknik doğrulama sınırlı; *confidence: low-to-medium*.

**Örnek 3 — Yanlış:**
> "Bu zafiyet kesinlikle kritik altyapıları etkileyecek."

**Örnek 3 — Doğru:**
> **Verified Facts:** [Kaynak], bu zafiyet sınıfının OT/ICS ortamlarında geçmişte istismar edildiğini bildirdi.
> **Analyst Assessment:** Benzer bir etkinin tekrarlanma olasılığı *likely* olarak değerlendiriliyor, ancak bu bir kesinlik iddiası değildir.

## Estimative Language Reference Table

| İfade | Yaklaşık olasılık aralığı |
|---|---|
| almost no chance | ~%0-5 |
| very unlikely | ~%5-20 |
| unlikely | ~%20-40 |
| roughly even chance | ~%40-60 |
| likely | ~%60-80 |
| very likely | ~%80-95 |
| almost certain | ~%95-100 |

*(ABD İstihbarat Topluluğu ICD 203 standardından uyarlanmıştır.)*

## Metodoloji Ağırlık Katmanları

| Katman | İçerik türleri | Gereksinim |
|---|---|---|
| Hafif | checklist, defensive-lesson | Bu ayrım zorunlu değil |
| Orta | attribution-sensitive olmayan sector-risk-note | Ayrım zorunlu, sözel güvenilirlik ölçeği yeterli |
| Ağır | incident-brief, threat-trend-report, attribution-sensitive içerik | Ayrım zorunlu + tam Admiralty Scale metadata (bkz. `source-reliability.md`) |

## Sık Yapılan Hatalar

- Analyst Assessment'ı "muhtemelen" gibi yumuşatıcı kelime kullanmadan, olgu gibi sunmak.
- Tek kaynaklı bir iddiayı Verified Facts'e koymak (tek kaynak = en fazla "low confidence" Analyst Assessment).
- Estimative language kullanmadan kesin olasılık ifadesi kullanmak ("kesinlikle", "şüphesiz").

## Reviewer Checklist Referansı

PR review yapan maintainer, her PR'da şu soruları sorar: Verified Facts bölümündeki her cümle birden fazla kaynakla destekleniyor mu? Analyst Assessment bölümü olgu gibi mi yazılmış? Estimative language doğru kullanılmış mı?
