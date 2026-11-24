# demli-arena

Demli kanalındaki model testlerinin **promptları ve ham çıktıları**. Videoda gördüğün her sonuç burada, kaynağıyla durur; isteyen aynı promptu kendisi çalıştırıp karşılaştırabilir.

## Kurallar

1. **Aynı prompt.** Her model aynı metni kelimesi kelimesine alır. Model adı, sistem istemi ve ayarlar `adisyon.json`'a yazılır.
2. **Tek atış.** İlk çıktı esastır. İkinci deneme yapılırsa ayrı dosya olur ve adisyonda görünür.
3. **Dürüst not.** Puan ve hüküm videodakiyle aynıdır. Çıktılar düzeltilmez, güzelleştirilmez; bozuk çıktı bozuk haliyle kalır.
4. **Ücret ve süre açık.** Süre, token ve maliyet ölçülebildiği kadar yazılır; ölçülemeyen alan `null` kalır, tahmin yazılmaz.

## Klasör düzeni

```
testler/
  <tarih>-<test-adı>/          ör. 2026-12-01-cay-ocagi-simulasyonu
    prompt.md                  modellere verilen metin, aynen
    sonuclar/
      <model>.html             modelin ham çıktısı (ör. claude-opus-5-5.html)
    adisyon.json               modeller, ayarlar, süre, maliyet, puan, hüküm
```

Yeni test için `testler/_sablon/` klasörünü kopyala ve adını değiştir. Şablon boştur; örnek veri içermez.

## adisyon.json alanları

| Alan | Ne |
|---|---|
| `test` | test adı |
| `tarih` | YYYY-AA-GG |
| `video` | videonun bağlantısı (yayından sonra) |
| `prompt_dosyasi` | genelde `prompt.md` |
| `kurallar` | tek atış mı, süre sınırı, araç izni |
| `modeller[]` | her model için: `ad`, `surum`, `arayuz`, `ayarlar`, `cikti`, `sure_sn`, `token`, `maliyet`, `puan`, `not` |
| `hukum` | kazanan ve bir cümlelik gerekçe |

## Lisans

Kod ve metinler MIT lisanslıdır (bkz. `LICENSE`). Model çıktıları ilgili sağlayıcıların kullanım koşullarına tabidir.
