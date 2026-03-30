# 🇹🇷 Türkiye İl, İlçe, Mahalle ve Sokak JSON Veritabanı

Türkiye'nin tüm illeri, ilçeleri, mahalleleri ve sokaklarını içeren kapsamlı JSON formatında bir veritabanıdır.

> **📚 Veri Kaynağı:** Bu proje [melihozkara/il-ilce-mahalle-sokak-veritabani](https://github.com/melihozkara/il-ilce-mahalle-sokak-veritabani) reposundan alınan verileri JSON formatına dönüştürmektedir.

---

## 📖 Kullanım

### Temel Yapı

Veritabanı aşağıdaki hiyerarşide organize edilmiştir:

```json
{
  "iller": [
    {
      "id": 1,
      "ad": "Adana",
      "ilceler": [
        {
          "id": 101,
          "ad": "Seyhan",
          "mahalleler": [
            {
              "id": 1001,
              "ad": "Bartin",
              "sokaklar": [
                {
                  "id": 10001,
                  "ad": "Cumhuriyet Caddesi"
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```

### Örnek Kullanımlar

#### JavaScript/Node.js

```javascript
const veritabani = require('./turkiye-il-ilce-mahalle-sokak.json');

// Tüm illeri listele
veritabani.iller.forEach(il => {
  console.log(il.ad);
});

// Belirli bir ili bul (Adana)
const adana = veritabani.iller.find(il => il.ad === 'Adana');

// Adana'nın ilçelerini listele
adana.ilceler.forEach(ilce => {
  console.log(`  - ${ilce.ad}`);
});

// Belirli bir ilçenin mahalleleri
const seyhan = adana.ilceler.find(ilce => ilce.ad === 'Seyhan');
console.log(`${seyhan.ad} ilçesinin mahalleleri:`, seyhan.mahalleler);
```

#### Python

```python
import json

with open('turkiye-il-ilce-mahalle-sokak.json', 'r', encoding='utf-8') as f:
    veritabani = json.load(f)

# Tüm illeri yazdır
for il in veritabani['iller']:
    print(f"İL: {il['ad']}")
    for ilce in il['ilceler']:
        print(f"  İLÇE: {ilce['ad']}")
        for mahalle in ilce['mahalleler']:
            print(f"    MAHALLE: {mahalle['ad']}")
```

---

## 🤝 Katkı

Bu projeye katkı sağlamak istiyorsanız, lütfen:

1. Repoyu fork edin
2. Yeni bir branch oluşturun (`git checkout -b feature/yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik: ...'`)
4. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
5. Bir Pull Request açın

### Veri Katkısı

Veri hataları veya eksiklikler için lütfen:
- [melihozkara/il-ilce-mahalle-sokak-veritabani](https://github.com/melihozkara/il-ilce-mahalle-sokak-veritabani) reposunda issue açınız
- Veya bu repo üzerinde doğrudan PR gönderiniz

---

## 📄 Lisans

Bu proje orijinal veri kaynağının lisansına uygun olarak dağıtılmaktadır.

---

## ⭐ Beğendiyseniz

Bu projeyi faydalı bulduysanız lütfen bir yıldız (⭐) vermeyi unutmayın!

---

**Sorular veya sorunlar için:** [Issue](https://github.com/si6n/turkiye-il-ilce-mahalle-sokak-json/issues) açınız.