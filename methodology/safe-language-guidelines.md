# Güvenli Dil İlkeleri

## Temel İlke

Tamga, "nasıl yapılır" (how to attack) bilgisini değil, "ne risk doğurur ve nasıl savunulur" (how to understand and defend) bilgisini üretir. Bu ayrım kelime seçiminde somutlaşır.

## Neden Önemli?

Bir tehdit sınıfını anlatırken kullanılan dil, içeriğin saldırı rehberi mi yoksa savunma analizi mi olduğunu belirler. Aynı teknik kavram iki şekilde de anlatılabilir — Tamga her zaman ikincisini seçer.

## Örnek Çiftler

| Kaçınılacak ifade | Tercih edilecek ifade |
|---|---|
| "Ağa nasıl sızılır" | "Yetkisiz erişim ve ön konumlanma riski" |
| "C2 nasıl gizlenir" | "Gizli komuta-kontrol iletişiminin tespit zorluğu" |
| "Veri nasıl silinir (wiper tekniği)" | "Veri bütünlüğünün bozulması riski ve kurtarma stratejisi" |
| "Zafiyet nasıl istismar edilir" | "Yamalanmamış sistemlerin kötüye kullanım riski" |
| "X aracı nasıl atlatılır" | "X aracının kapsamadığı senaryo, ek kontrol gerekliliği" |

## Pratik Kural

Bir cümle yazıldıktan sonra şu testi uygulayın: *Bu cümle, bir saldırganın elini güçlendiren bir adım mı, yoksa bir savunmacının dikkatini doğru yere yönlendiren bir gözlem mi?* İlk durumda cümle yeniden yazılır veya çıkarılır.

## Panik Yaratan Dilden Kaçınma

"Tek komutla çökertilebilir" gibi abartılı, gerçek dışı ifadeler kullanılmaz. Risk, ölçülü ve doğru orantılı bir dille anlatılır.

## Bu İlke Hangi İçeriklerde Daha Kritik?

`malware-threat-analysis` ve `ai-safety-lab` repolarında bu ilke özellikle sıkı uygulanır, çünkü buradaki konular (malware davranışı, prompt injection) doğası gereği kötüye kullanıma daha yakın durabilir. Her PR review'unda reviewer, içeriğin "anlamak için" mi yoksa "yapmak için" mi yazıldığını sorar.
