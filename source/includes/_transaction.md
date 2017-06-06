# Transaction


## Get User's Transaction


## Checkout Cart to Transaction

<aside class="warning">Need Authitencation.</aside>

### HTTP Request

`POST https://shoupbud.xyz/api/transaction`


```shell
curl -X GET \
  https://shoupbud.xyz/api/transaction \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache'
```

> Response Sukses

```json
{
  "id": 56,
  "nominal": 400000,
  "nominal_string": "Rp. 400.000",
  "user": {
      "id": 45,
      "name": "Nipe Harefa Test Other User",
      "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
  },
  "type": "User",
  "status": 2,
  "status_string": "Fail / Cancel",
  "updated_at": "2017-06-05T10:19:34+00:00",
  "links": {
      "approve": "/api/admin/transaction/56/approve",
      "cancel": "/api/admin/transaction/56/cancel"
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
            "small": "https://shoupbud.xyz/image/small/hMFsDR4NDVq8BZ11TqrT.jpg",
            "medium": "https://shoupbud.xyz/image/medium/hMFsDR4NDVq8BZ11TqrT.jpg",
            "large": "https://shoupbud.xyz/image/large/hMFsDR4NDVq8BZ11TqrT.jpg"
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
```


> Response Fail(400)

```json
{
  "message": "Saldo tidak cukup"
}
```