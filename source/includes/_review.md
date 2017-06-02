# Review

## Create a Review

<aside class="notice">
Requires authentication.
</aside>

Parameter | | Description
--------- | --------- | -----------
`product_id` | required | Product ID
`vendor_id` | 'filename|blob' required | Vendor ID
`rating` | required | Rating
`body` | required | Review Text 

```shell
curl -X POST \
  https://shoupbud.xyz/api/review \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -F product_id=31 \
  -F vendor_id=44 \
  -F rating=4 \
  -F 'body=barangnya mantap dan bagus'
```

> Response Sukses (201)

```json
{
  "status": "OK",
  "review": {
      "id": 76,
      "rating": "4",
      "body": "barangnya mantap dan bagus",
      "sentimen": {
        "detail": {
          "pos": 0.615,
          "neu": 0.308,
          "neg": 0.077
        },
        "category": "pos"
      },
      "user": {
        "id": 39,
        "name": "Nipe",
        "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
      },
      "product": {
        "id": 31,
        "name": "UHU Perekat Serbaguna",
        "category": {
            "id": 1,
            "name": "Uncategorized",
            "slug": "uncategorized",
            "description": null
        },
        "barcode": 40206700407563,
        "picture_url": {
            "small": "https://shoupbud.xyz/image/small/xw6NAomKz8fxkLXbL86a.jpg",
            "medium": "https://shoupbud.xyz/image/medium/xw6NAomKz8fxkLXbL86a.jpg",
            "large": "https://shoupbud.xyz/image/large/xw6NAomKz8fxkLXbL86a.jpg"
        },
        "description": "",
        "vendors": [
            {
                "id": 10,
                "name": "UHU Perekat Serbaguna",
                "picture_url": {
                    "small": "https://shoupbud.xyz/images/small/xw6NAomKz8fxkLXbL86a.jpg",
                    "medium": "https://shoupbud.xyz/images/medium/xw6NAomKz8fxkLXbL86a.jpg",
                    "large": "https://shoupbud.xyz/images/large/xw6NAomKz8fxkLXbL86a.jpg"
                },
                "price": 1525,
                "price_string": 1525,
                "barcode": "40206700407563",
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
        "minimum_price": 1525,
        "minumumPrice": 1525,
        "liked": true,
        "recentReview": []
      },
      "vendor": {
        "id": 44,
        "name": "PT. Alfamart Indonesia",
        "picture_url": null,
        "total_product": 1,
        "total_review": 0
      }
  },
  "message": null
}
```

## Get Review


Parameter | | Description
--------- | --------- | -----------
`user_id` | optional | User ID
`product_id` | optional | Product ID
`vendor_id` | optional | Vendor ID

```shell
curl -X GET \
  'https://shoupbud.xyz/api/review?user_id=39&product_id=31' \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW'
```

```json
{
    "status": "OK",
    "message": null,
    "reviews": [
        {
            "id": 76,
            "rating": 4,
            "body": "barangnya mantap dan bagus",
            "sentimen": {
                "detail": {
                    "pos": 0.615,
                    "neu": 0.308,
                    "neg": 0.077
                },
                "category": "pos"
            },
            "user": {
                "id": 39,
                "name": "Nipe",
                "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
            },
            "product": {
                "id": 31,
                "name": "UHU Perekat Serbaguna",
                "category": {
                    "id": 1,
                    "name": "Uncategorized",
                    "slug": "uncategorized",
                    "description": null
                },
                "barcode": 40206700407563,
                "picture_url": {
                    "small": "https://shoupbud.xyz/image/small/xw6NAomKz8fxkLXbL86a.jpg",
                    "medium": "https://shoupbud.xyz/image/medium/xw6NAomKz8fxkLXbL86a.jpg",
                    "large": "https://shoupbud.xyz/image/large/xw6NAomKz8fxkLXbL86a.jpg"
                },
                "description": "",
                "vendors": [
                    {
                        "id": 10,
                        "name": "UHU Perekat Serbaguna",
                        "picture_url": {
                            "small": "https://shoupbud.xyz/images/small/xw6NAomKz8fxkLXbL86a.jpg",
                            "medium": "https://shoupbud.xyz/images/medium/xw6NAomKz8fxkLXbL86a.jpg",
                            "large": "https://shoupbud.xyz/images/large/xw6NAomKz8fxkLXbL86a.jpg"
                        },
                        "price": 1525,
                        "price_string": 1525,
                        "barcode": "40206700407563",
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
                "minimum_price": 1525,
                "minumumPrice": 1525,
                "liked": true,
                "recentReview": []
            },
            "vendor": {
                "id": 44,
                "name": "PT. Alfamart Indonesia",
                "picture_url": null,
                "total_product": 1,
                "total_review": 0
            }
        }
    ]
}
```

## Update Review

Parameter | | Description
--------- | --------- | -----------
`id_review| required | ID Review
`product_id` | required | Product ID
`vendor_id` | 'filename|blob' required | Vendor ID
`rating` | required | Rating
`body` | required | Review Text 


> Sample Request

```shell
curl -X PUT \
  https://shoupbud.xyz/api/review/id_review \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -H 'postman-token: 3b50176e-388a-db87-ee14-d5c132a111d9' \
  -d 'product_id=31&vendor_id=44&rating=3&body=bagus%20bagus'
```

> Response Sukses (200)

```json
{
  "status": "OK",
  "review": {
    "id": 76,
    "rating": "3",
    "body": "bagus bagus",
    "sentimen": {
      "pos": 0.571,
      "neu": 0.286,
      "neg": 0.143
    },
    "user": {
      "id": 39,
      "name": "Nipe",
      "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
    },
    "product": {
      "id": 31,
      "name": "UHU Perekat Serbaguna",
      "category": {
        "id": 1,
        "name": "Uncategorized",
        "slug": "uncategorized",
        "description": null
      },
      "barcode": 40206700407563,
      "picture_url": {
        "small": "http://skripsi.home.dev/image/small/xw6NAomKz8fxkLXbL86a.jpg",
        "medium": "http://skripsi.home.dev/image/medium/xw6NAomKz8fxkLXbL86a.jpg",
        "large": "http://skripsi.home.dev/image/large/xw6NAomKz8fxkLXbL86a.jpg"
      },
      "description": "",
      "vendors": [
        {
          "id": 10,
          "name": "UHU Perekat Serbaguna",
          "picture_url": {
            "small": "http://skripsi.home.dev/images/small/xw6NAomKz8fxkLXbL86a.jpg",
            "medium": "http://skripsi.home.dev/images/medium/xw6NAomKz8fxkLXbL86a.jpg",
            "large": "http://skripsi.home.dev/images/large/xw6NAomKz8fxkLXbL86a.jpg"
          },
          "price": 1525,
          "price_string": 1525,
          "barcode": "40206700407563",
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
      "minimum_price": 1525,
      "minumumPrice": 1525,
      "liked": true,
      "recentReview": []
    },
    "vendor": {
      "id": 44,
      "name": "PT. Alfamart Indonesia",
      "picture_url": null,
      "total_product": 1,
      "total_review": 0
    }
  },
  "message": null
}
```