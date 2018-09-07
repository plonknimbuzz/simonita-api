# Simonita API

## Usage
Kirim request melalui post (preferred) atau get ke alamat: `http://domain/simonita/api/json/method?param`

## Method

### Analisis
Untuk mendapatkan analisis beserta resume nya


| param | type | required | keterangan |
|---|---|---|---|
|tipe   |string   | no   | Tipe analisis (cetak (pagi), online (sore)). Default= online   |
|tanggal   |string   | no   | tanggal analisis, format Y-m-d. Default= current date   |

example:

`http://domain/simonita/api/json/analisis?tipe=cetak&tanggal=2018-09-01`

output:
```json
{
  "ok": 1,
  "data": {
    "analysis_id": 11900,
    "tipe_media": "cetak",
    "tanggal": "2018-09-07",
    "judul": "PPh Impor Perkuat Industri Nasional",
    "prolog": null,
    "epilog": "isi epilog",
    "item": [
      {
        "judul": "PPh Impor Perkuat Industri Nasional",
        "isi": "isi analisis",
        "tipe": "headline"
      },
      //...
    ],
    "resume": [
      {
        "kliping_id": 609531,
        "judul": "Pemerintah Sisir Proyek Strategis",
        "hal": "4",
        "tanggal": "2018-09-07",
        "media": "Bisnis Indonesia"
      },
      //...
    ]
  }
}
```

### Sentimen
untuk mendapatkan jumlah tone/sentimen pemberitaan per tanggal

| param | type | required | keterangan |
|---|---|---|---|
|dari   |string   | no   | rentang tanggal awal, format Y-m-d. Default= current date   |
|ke   |string   | no   | rentang tanggal akhir, format Y-m-d. Default= current date   |


contoh:

`http://domain/simonita/api/json/sentimen?dari=2018-09-01&ke=2018-09-07`

output:
```json
{
  "ok": 1,
  "data": {
    "2018-09-01": [
      70,
      22,
      13
    ],
    "2018-09-02": [
      40,
      24,
      4
    ],
    //...
  }
}

```

### Media
untuk mendapatkan jumlah media per tanggal

| param | type | required | keterangan |
|---|---|---|---|
|dari   |string   | no   | rentang tanggal awal, format Y-m-d. Default= current date   |
|ke   |string   | no   | rentang tanggal akhir, format Y-m-d. Default= current date   |


contoh:

`http://domain/simonita/api/json/media?dari=2018-09-01&ke=2018-09-07`

output:
```json
{
  "ok": 1,
  "data": {
    "bisnis.com": 172,
    "kontan.co.id": 165,
    "Liputan6.com": 142,
    "Detik.Com": 141,
    "Republika Online": 137,
    "metrotvnews.com": 97,
    "Merdeka.com": 96,
    "tribunnews": 89,
    "Okezone.com": 81,
    "CNN": 80
  }
}
```


