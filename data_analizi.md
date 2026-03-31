# data.xlsx — Veri Seti Analizi

## Genel Bakış

Bu dosya, **21.2 GHz frekanslı** ve **2.8 km mesafeli** bir mikrodalga radyo bağlantısına ait ölçüm verisi içermektedir.

- **Kapsanan dönem:** 1 Haziran 2014 – 2 Temmuz 2014 (~1 ay)
- **Amaç:** Muhtemelen yağış kaynaklı sinyal zayıflaması (rain attenuation) araştırması
- **İklim profili:** Sıcak ve kurak bölge (yüksek sıcaklık, düşük nem, az yağış)

---

## Sayfa 1: `21.2GHz 2.8 km`

**15 dakikalık** aralıklarla alınan RSL/TSL ölçümleri.

- **Toplam kayıt:** 2.606
- **Cihaz:** KHB027 koukou-55-ODU-1 (RTNRF-1)

### Sütunlar

| Sütun | Açıklama |
|-------|----------|
| Resource Name | Cihaz/bağlantı adı |
| Collection Time | Ölçüm zamanı (UTC+3) |
| Granularity | Ölçüm granülaritesi (15 dakika) |
| RSL_MAX | 15 dk içindeki maksimum alınan sinyal gücü (dBm) |
| RSL_MIN | 15 dk içindeki minimum alınan sinyal gücü (dBm) |
| TSL_MAX | 15 dk içindeki maksimum iletilen sinyal gücü (dBm) |
| TSL_MIN | 15 dk içindeki minimum iletilen sinyal gücü (dBm) |

### İstatistikler

| Metrik | Değer |
|--------|-------|
| RSL_MAX aralığı | -45.70 dBm ~ -42.30 dBm |
| RSL_MAX ortalaması | -44.50 dBm |
| TSL_MAX / TSL_MIN | Sabit **-55 dBm** (verici gücü değişmemiş) |

---

## Sayfa 2: `Sheet2`

**1 dakikalık** çözünürlükte meteorolojik ve RF sinyal ölçümleri.

- **Toplam kayıt:** 39.074
- **Dönem:** 1 Haziran 2014 21:00 – 2 Temmuz 2014 07:29

### Sütunlar

| Sütun | Açıklama |
|-------|----------|
| History file UTC Time | Ölçüm zamanı |
| MOR_1A | Meteorolojik Optik Menzil — görüş mesafesi (m) |
| TEMP (°C) | Hava sıcaklığı |
| RH (%) | Bağıl nem |
| PAINS (HPA) | Atmosferik basınç |
| 1H RAIN (MM) | Saatlik yağış miktarı |
| WSINS (KT) | Rüzgar hızı (knot) |
| RSL | Anlık alınan sinyal seviyesi (dBm) |
| Reference | Referans RSL değeri (dBm) |
| dB | Sinyal zayıflaması (dB) |
| dB/km | Spesifik zayıflama (dB/km) |

### İstatistikler

| Metrik | Min | Max | Ortalama |
|--------|-----|-----|----------|
| MOR (görüş mesafesi, m) | 100 | 10.000 | 8.688 |
| Sıcaklık (°C) | 25.1 | 44.7 | 35.7 |
| Bağıl nem (%) | 6 | 74 | 21.6 |
| Yağış (mm/saat) | 0 | 0.6 | ~0 |
| RSL (dBm) | -53.2 | -44.1 | -45.65 |
| Zayıflama (dB) | 0.3 | 9.4 | 1.85 |
| Spesifik zayıflama (dB/km) | 0.11 | 3.36 | 0.66 |

---

## Genel Değerlendirme

1. **Verici gücü sabittir** — TSL tüm ölçümler boyunca -55 dBm'de sabit kalmış, dolayısıyla RSL'deki değişimler tamamen kanal koşullarından kaynaklanmaktadır.

2. **Yağış oldukça nadirdir** — 1 aylık sürede saatlik yağış nadiren 0.6 mm'yi geçmiştir. Bu durum, veri setinin **kurak iklim koşullarını** temsil ettiğine işaret eder.

3. **Sinyal zayıflaması anlamlı farklılık göstermektedir** — RSL değerleri -44.1 ile -53.2 dBm arasında değişmekte; maksimum 9.4 dB'lik zayıflama gözlemlenmiştir. Bu, yağışsız dönemlerde bile zayıflamanın yaşandığını gösterir (muhtemelen nem veya buharlaşmadan kaynaklı).

4. **Meteoroloji-RF korelasyonu** — MOR, sıcaklık, nem ve yağış verileriyle RSL/zayıflama değerleri eş zamanlı tutulmuştur. Bu yapı, meteorolojik parametrelerin sinyal üzerindeki etkisini modellemeye uygundur.
