# Cart

## Get List Cart


```shell
curl -X GET \
  https://shoupbud.xyz/api/cart \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache'
```

> Response Sukses(200)

```json
{
    "data": "OK",
    "message": null,
    "carts": {
      "items": [
        {
          "id": 2,
          "items": {
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
          },
          "total": 1525,
          "quantity": 1
        }
      ],
      "total": 1525,
      "total_strings": ""
    }
}
```

## Add Product to Cart

### URL Parameters

Parameter | Description
--------- | -----------
product_vendor_id | Product Vendor Id
quantity | Quantity

Pada proses ini quantity bersifat `optional` dan mempunyai nilai default `1`.

```shell
curl -X POST \
  https://shoupbud.xyz/api/cart \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -F product_vendor_id= \ 
  -F quantity=2
```

> Response Sukses (200)

```json
{
    "cart": {
        "id": 44,
        "name": "PT. Alfamart Indonesia OK",
        "email": "info@alfamart.com",
        "phone": "6282229111",
        "picture_url": "jAYeIlTucpi7gZh9qhYG.jpg",
        "saldo": 0,
        "role": 2,
        "address": "asdfasdf",
        "confirmed": 1,
        "latitude": null,
        "longitude": 98.61,
        "created_at": "2017-04-26 14:30:01",
        "updated_at": "2017-06-14 14:15:18",
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
        },
        "item": [
            {
                "id": 4,
                "cart_id": 3,
                "product_vendor_id": 10,
                "quantity": 3,
                "price": 4575,
                "created_at": "2017-06-30 23:18:44",
                "updated_at": "2017-06-30 23:18:44"
            }
        ]
    },
    "message": "Added",
    "status": "OK"
}
```

> Response Fail(400)

```json
{
  "status": "ERROR",
  "cart": null,
  "message": "Cek input"
}
```

## Update Cart


### Parameters

Parameter | Description
--------- | -----------
cartId | Detail Cart ID
cartDetailId | Detail Cart ID


```shell
curl -X PUT \
  https://shoupbud.xyz/api/cart/cartId/detail/cartDetailId \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -d quantity=2
```

> Response Sukses(200)

```json
{
    "cart": {
        "id": 44{
    "cart": {
        "id": 44,
        "name": "PT. Alfamart Indonesia OK",
        "email": "info@alfamart.com",
        "phone": "6282229111",
        "picture_url": "jAYeIlTucpi7gZh9qhYG.jpg",
        "saldo": 0,
        "role": 2,
        "address": "asdfasdf",
        "confirmed": 1,
        "latitude": null,
        "longitude": 98.61,
        "created_at": "2017-04-26 14:30:01",
        "updated_at": "2017-06-14 14:15:18",
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
        },
        "item": [
            {
                "id": 3,
                "cart_id": 3,
                "product_vendor_id": 10,
                "quantity": 2,
                "price": 3050,
                "created_at": "2017-06-30 23:01:04",
                "updated_at": "2017-06-30 23:08:55"
            }
        ]
    },
    "message": null,
    "status": "OK"
}
```

> Response Fail (400)

```json
{
  "status": "ERROR",
  "message": "No query",
  "cart": null
}
```

## Delete Cart

Parameter | Description
--------- | -----------
cart_id | Cart ID


```shell
curl -X DELETE \
  https://shoupbud.xyz/api/cart/cart_id \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache'
```

> Response Fail (400)

```json
{
  "status": "ERROR",
  "message": "Something wrong"
}
```

## Delete Item Cart

Parameter | Description
--------- | -----------
cartId | Detail Cart ID
cartDetailId | Detail Cart ID


```shell
curl -X DELETE \
  https://shoupbud.xyz/api/cart/cartId/detail/cartDetailId \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache'
```

> Response Success (204)

```json
```

> Response Fail (400)

```json
{
  "status": "ERROR",
  "message": "Something wrong"
}
```