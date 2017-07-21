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

## Pagination

### Parameters

| name    |              | Description   |
|---------|--------------|---------------|
| page    | default = 1  | Page          |
| peritem | default = 10 | Item Per Page |

```sh
curl -X GET \
  'https://shoupbud.xyz/api/product?page=1&perpage=1' \
  -H 'cache-control: no-cache' \
```

```json
{
    "status": "OK",
    "products": [
        {
            "id": 8,
            "name": "LOTTE xylitol chewing gum fresh mint",
            "category": {
                "id": 4,
                "name": "Snacks",
                "slug": "snacks",
                "picture_url": "etwebdUm4IzqQYvBHakE.jpg",
                "description": null
            },
            "barcode": 8990333164055,
            "description": "Lotte Xylitol merupakan permen karet yang memiliki fungsi mengurangi resiko gigi berlubang.",
            "picture_url": {
                "small": "https://shoupbud.xyz/image/small/6Py4Ti42Tqm1gQu50gRF.jpg",
                "medium": "https://shoupbud.xyz/image/medium/6Py4Ti42Tqm1gQu50gRF.jpg",
                "large": "https://shoupbud.xyz/image/large/6Py4Ti42Tqm1gQu50gRF.jpg"
            },
            ....
        }
    ],
    "message": null,
    "link": {
        "next": "http://shoupbud.xyz/api/product?page=2"
    }
}
```

## Get Popular Product

### Parameters

| name    |              | Description   |
|---------|--------------|---------------|
| page    | default = 1  | Page          |
| perpage | default = 10 | Item Per Page |


```sh
curl -X GET \
  'https://shoupbud.xyz/api/product/trending?perpage=10&page=1' \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token'
```

```json
{
    "messge": null,
    "products": [
        {
            "id": 18,
            "name": "Mylanta Antasid Obat Maag 150ml",
            "category": {
                "id": 9,
                "name": "Uncategorized",
                "slug": "uncategorized",
                "picture_url": null,
                "description": null
            },
            "barcode": 899275051226,
            "description": "Alice, 'because I'm not looking for it, you may SIT down,' the King said, with a sudden burst of tears, 'I do wish they COULD! I'm sure I can't be civil, you'd better ask HER about it.' 'She's in.",
            "picture_url": {
                "small": "http://https://shoupbud.xyz/image/small/skripsi-mylanta-antasid-obat-maag-150ml.jpg",
                "medium": "http://https://shoupbud.xyz/image/medium/skripsi-mylanta-antasid-obat-maag-150ml.jpg",
                "large": "http://https://shoupbud.xyz/image/large/skripsi-mylanta-antasid-obat-maag-150ml.jpg"
            },
            "vendors": [
                {
                    "id": 14,
                    "name": "Mylanta Antasid Obat Maag 150ml",
                    "picture_url": {
                        "small": "http://https://shoupbud.xyz/image/small/skripsi-mylanta-antasid-obat-maag-150ml.jpg",
                        "medium": "http://https://shoupbud.xyz/image/medium/skripsi-mylanta-antasid-obat-maag-150ml.jpg",
                        "large": "http://https://shoupbud.xyz/image/large/skripsi-mylanta-antasid-obat-maag-150ml.jpg"
                    },
                    "price": 3586,
                    "price_string": "Rp. 3.586",
                    "barcode": "899275051226",
                    "vendor": {
                        "id": 9,
                        "name": "Dr. Lavinia Wintheiser III",
                        "email": "nellie15@example.net",
                        "confirmed": true,
                        "picture_url": "skripsi-gilfoyle.jpg",
                        "total_product": 10,
                        "total_review": 0,
                        "lat": -61.03305,
                        "lng": 118.7045
                    }
                }
            ],
            "total_review": 1,
            "total_vendor": 1,
            "total_rating": 1,
            "avg_rating": 4,
            "minimum_price": 3586,
            "minimum_price_string": "Rp. 3.586",
            "minumumPrice": 3586,
            "liked": false,
            "recentReview": [],
            "summary": {
                "mean": {
                    "pos": 0.667,
                    "neg": 0.167,
                    "neu": 0.167
                },
                "count": {
                    "pos": 1,
                    "neg": 0,
                    "neu": 0
                }
            },
            "summary_string": "pos"
        }
    ],
    "pagination": {
        "prev": null,
        "next": null,
        "total": 1
    }
}
```


## Get Newest Product


### Parameters

| name    |              | Description   |
|---------|--------------|---------------|
| page    | default = 1  | Page          |
| perpage | default = 10 | Item Per Page |


```sh
curl -X GET \
  'https://shoupbud.xyz/api/product/newest?perpage=1&page=1' \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token'
```

```json
{
    "messge": null,
    "products": [
        {
            "id": 15,
            "name": "Aqua Mineral Botol 600ml",
            "category": {
                "id": 9,
                "name": "Uncategorized",
                "slug": "uncategorized",
                "picture_url": null,
                "description": null
            },
            "barcode": 3030552300010,
            "description": "Alice, that she knew she had known them all her life. Indeed, she had accidentally upset the week before. 'Oh, I BEG your pardon!' cried Alice (she was rather glad there WAS no one could possibly.",
            ....
        }
    ],
    "pagination": {
        "prev": null,
        "next": "http://https://shoupbud.xyz/api/product/newest?page=2",
        "total": 10
    }
}
```