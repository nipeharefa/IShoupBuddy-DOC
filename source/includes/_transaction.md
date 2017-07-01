# Transaction


## Get User's Transaction

<aside class="warning">Need Authitencation.</aside>

### HTTP Request

`GET https://shoupbud.xyz/api/transaction?with=d`

```shell
curl -X GET \
  'http://skripsi.home.dev/api/transaction?with=d' \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' 
```

```json
{
  "message": null,
  "status": "OK",
  "transactions": [
    {
      "id": 4,
      "nominal": 400000,
      "nominal_string": "Rp. 400.000",
      "user": {
        "id": 45,
        "name": "Nipe Harefa Test Other User",
        "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
      },
      "type": "User",
      "status": 0,
      "status_string": "Pending",
      "updated_at": "2017-06-06T14:35:17+00:00",
      "links": {
        "approve": "/api/admin/transaction/4/approve",
        "cancel": "/api/admin/transaction/4/cancel"
      },
      "detail": [
        {
          "id": 2,
          "quantity": 2,
          "harga": 200000,
          "harga_string": "Rp. 200.000",
          "total": 400000,
          "total_string": "Rp. 400.000",
          "item": {
            "id": 11,
            "name": "Mylanta Obat Maag Liquid 150Ml",
            "picture_url": {
              "small": "http://skripsi.home.dev/image/small/hMFsDR4NDVq8BZ11TqrT.jpg",
              "medium": "http://skripsi.home.dev/image/medium/hMFsDR4NDVq8BZ11TqrT.jpg",
              "large": "http://skripsi.home.dev/image/large/hMFsDR4NDVq8BZ11TqrT.jpg"
            },
            "price": 100000,
            "price_string": "Rp. 100.000",
            "barcode": "899275051226",
            "vendor": {
              "id": 44,
              "name": "PT. Alfamart Indonesia",
              "email": "info@alfamart.com",
              "confirmed": true,
              "picture_url": null,
              "total_product": 6,
              "total_review": 0
            }
          }
        }
      ]
    }
  ]
}
```

## Checkout Cart to Transaction

<aside class="warning">Need Authitencation.</aside>

### HTTP Request

`POST https://shoupbud.xyz/api/transaction`

### Parameters

| name    |                | Description                       |
|---------|----------------|-----------------------------------|
| cart_id | required|array | Array Cart Id yang ingin checkout |
|         |                |                                   |


```shell
curl -X POST \
  https://shoupbud.xyz/api/transaction \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: b41358a3-0bbf-8da4-880c-21e98160aae8' \
  -d '{
  "cart_id": [1]
}'
```

> Response Sukses

```json
[
    {
        "id": 43,
        "nominal": 4575,
        "nominal_string": "Rp. 4.575",
        "user": {
            "id": 45,
            "name": "Nipe Harefa Test Other User",
            "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
        },
        "type": "User",
        "status": 1,
        "status_string": "Success",
        "updated_at": "2017-07-01T22:05:41+07:00",
        "links": {
            "approve": "/api/admin/transaction/43/approve",
            "cancel": "/api/admin/transaction/43/cancel"
        },
        "detail": [
            {
                "id": 25,
                "name": "UHU Perekat Serbaguna",
                "quantity": 3,
                "harga": 1525,
                "harga_string": "Rp. 1.525",
                "total": 4575,
                "total_string": "Rp. 4.575",
                "item": {
                    "id": 10,
                    "name": "UHU Perekat Serbaguna",
                    "picture_url": {
                        "small": "http://skripsi.home.dev/image/small/xw6NAomKz8fxkLXbL86a.jpg",
                        "medium": "http://skripsi.home.dev/image/medium/xw6NAomKz8fxkLXbL86a.jpg",
                        "large": "http://skripsi.home.dev/image/large/xw6NAomKz8fxkLXbL86a.jpg"
                    },
                    "price": 1525,
                    "price_string": "Rp. 1.525",
                    "barcode": "40206700407563",
                    "vendor": {
                        "id": 44,
                        "name": "PT. Alfamart Indonesia OK",
                        "email": "info@alfamart.com",
                        "confirmed": true,
                        "picture_url": "jAYeIlTucpi7gZh9qhYG.jpg",
                        "total_product": 6,
                        "total_review": 0,
                        "lat": null,
                        "lng": 98.61
                    }
                }
            }
        ]
    }
]
```


> Response Fail(400)

```json
{
    "message": "No query results for model [App\\Models\\Cart] 1"
}
```