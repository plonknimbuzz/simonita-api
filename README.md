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
      {
        "judul": "PPh Impor Perkuat Industri Nasional",
        "isi": "isi analisis",
        "tipe": "headline"
      }
    ],
    "resume": [
      {
        "kliping_id": 609531,
        "judul": "Pemerintah Sisir Proyek Strategis",
        "hal": "4",
        "tanggal": "2018-09-07",
        "media": "Bisnis Indonesia"
      },
      {
        "kliping_id": 609531,
        "judul": "Pemerintah Sisir Proyek Strategis",
        "hal": "4",
        "tanggal": "2018-09-07",
        "media": "Bisnis Indonesia"
      }
    ]
  }
}
```
