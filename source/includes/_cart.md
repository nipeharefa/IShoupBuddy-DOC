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
product_id | Product Id
vendor_id | Vendor ID
quantity | Quantity

Pada proses ini quantity bersifat `optional` dan mempunyai nilai default `1`.

```shell
curl -X POST \
  https://shoupbud.xyz/api/cart \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -F product_id=3 \
  -F vendor_id= \ 
  -F quantity=2
```

> Response Sukses (200)

```json
{
  "status": "OK",
  "cart": {
    "id": 4,
    "items": {
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
    },
    "total": 4575,
    "quantity": "3"
  },
  "message": "Cart added"
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


Parameter | Description
--------- | -----------
cart_id | Cart ID


```shell
curl -X PUT \
  http://skripsi.home.dev/api/cart/2 \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -d quantity=1
```

> Response Sukses(200)

```json
{
  "status": "OK",
  "cart": {
    "id": 2,
    "items": {
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
    },
    "total": 1525,
    "quantity": "1"
  },
  "messaage": "updated"
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
  http://skripsi.home.dev/api/cart/cart_id \
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