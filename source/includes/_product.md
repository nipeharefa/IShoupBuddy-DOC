# Product

## Get List Produk

Untuk mendapatkan daftar produk yang terdaftar di database tanpa parameter. Jika tedapat parameter tambahan seperti `keyword` maka response akan disesuaikan dengan value dari parameter, dan dapat menggunakan lebih dari satu parameter.  


Parameter | Description
--------- | -----------
`keyword` | Hanya menampilkan produk sesuai dengan keywor
`category_id` | Hanya menampilkan produk dengan kategori tertentu
`vendor_id | Hanya menampilkan produk dengan vendor tertentu

```shell
Menampilkan semua Produk

curl -X GET \
  https://shoupbud.xyz/api/product \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache'


Menampilkan produk dengan ketegori spesifik

curl -X GET \
  https://shoupbud.xyz/api/product?category_id=1 \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache'

Menampilkan produk dengan penggabungan parameter categori_id dan keyword

curl -X GET \
  'https://shoupbud.xyz/api/product?category_id=1&keyword=hit' \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache'

```

> Response Sukses (200)

```json
{
  "status": "OK",
  "products": [
    {
      "id": 24,
      "name": "Soffel Kulit Jeruk 80g",
      "category": {
        "id": 1,
        "name": "Uncategorized",
        "slug": "uncategorized",
        "description": null
      },
      "barcode": 8992772315128,
      "picture_url": {
        "small": "https://shoupbud.xyz/image/small/ce7NxJ8vBdTEHcGMMuif.jpg",
        "medium": "https://shoupbud.xyz/image/medium/ce7NxJ8vBdTEHcGMMuif.jpg",
        "large": "https://shoupbud.xyz/image/large/ce7NxJ8vBdTEHcGMMuif.jpg"
      },
      "description": "",
      "vendors": [
        {
          "id": 2,
          "name": "Soffel Kulit Jeruk 80g",
          "price": 100000,
          "price_string": 100000,
          "barcode": "8992772315128",
          "vendor": {
            "id": 44,
            "name": "PT. Alfamart Indonesia",
            "picture_url": null,
            "total_product": 1,
            "total_review": 0
          }
        }
      ],
      "total_review": 0,
      "total_vendor": 1,
      "total_rating": 0,
      "minimum_price": 100000
    }
  ],
  "message": null
}
```

## Get Product By Barcode

Parameter | | Description
--------- | --------- | -----------
`product_barcode` | required | Product's baracode

```shell
curl -X GET \
  https://shoupbud.xyz/api/product/barcode/product_barcode \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
```

> Response Sukses (200)

```json
{
  "status": "OK",
  "product": {
    "id": 15,
    "name": "Soffel Kuli tJeruk 80g",
    "category": {
      "id": 1,
      "name": "Uncategorized",
      "slug": "uncategorized",
      "description": null
    },
    "barcode": 8992772315128,
    "picture_url": {
      "small": "https://shoupbud.xyz/image/small/IMG_1571.JPG",
      "medium": "https://shoupbud.xyz/image/medium/IMG_1571.JPG",
      "large": "https://shoupbud.xyz/image/large/IMG_1571.JPG"
    },
    "description": ""
  },
  "message": null
}
```

> Response Fail (404)

```json
{
  "status": "OK",
  "product": null,
  "message": "Produk tidak ditemukan"
}
```

## Get Details Product


```shell
curl -X GET \
  https://shoupbud.xyz/api/product/24 \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'postman-token: 06b8d7ba-15fa-22c2-a695-ce076287d318'
```

> Response Sukses (200)

```json
{
  "status": "OK",
  "product": {
    "id": 24,
    "name": "Soffel Kulit Jeruk 80g",
    "category": {
      "id": 1,
      "name": "Uncategorized",
      "slug": "uncategorized",
      "description": null
    },
    "barcode": 8992772315128,
    "picture_url": {
      "small": "https://shoupbud.xyz/image/small/ce7NxJ8vBdTEHcGMMuif.jpg",
      "medium": "https://shoupbud.xyz/image/medium/ce7NxJ8vBdTEHcGMMuif.jpg",
      "large": "https://shoupbud.xyz/image/large/ce7NxJ8vBdTEHcGMMuif.jpg"
    },
    "description": "",
    "vendors": [
      {
        "id": 2,
        "name": "Soffel Kulit Jeruk 80g",
        "price": 100000,
        "price_string": 100000,
        "barcode": "8992772315128",
        "vendor": {
          "id": 44,
          "name": "PT. Alfamart Indonesia",
          "picture_url": null,
          "total_product": 1,
          "total_review": 0
        }
      }
    ],
    "total_review": 0,
    "total_vendor": 1,
    "total_rating": 0,
    "minimum_price": 100000
  },
  "message": null
}
```

> Response Fail (404)

```json
{
  "status": "ERROR",
  "product": [],
  "message": "Produk tidak ditemukan"
}
```

## Get Statistik Produk

Parameter | | Description
--------- | --------- | -----------
`vendor_id` | required | Vendor Id
`product_id` | required | Product Id
`range` | optional | Range statistik dalam janga waktu tertentu. Misalnya `7` untuk 1 minggu terakhir, `30` untuk 1 bulan terakhir,  `90` untuk 3 bulan terakhir, dan seterusnya.

```shell
curl -X GET \
  'https://shoupbud.xyz/api/statistic?vendor_id=44&product_id=31' \
  -H 'cache-control: no-cache'
```

> Response Sukses (200)

```json
{
  "status": "OK",
  "message": null,
  "statistic": [
    {
      "id": 3,
      "value": 1000,
      "date": "2017-02-09T14:58:29+00:00",
      "vendor": 44,
      "product": 31
    },
    {
      "id": 4,
      "value": 1000,
      "date": "2017-05-09T14:58:29+00:00",
      "vendor": 44,
      "product": 31
    },
    {
      "id": 5,
      "value": 1525,
      "date": "2017-05-10T02:57:05+00:00",
      "vendor": 44,
      "product": 31
    }
  ]
}
```