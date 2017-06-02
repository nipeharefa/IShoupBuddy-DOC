# Wishlist

## Get Account Wishlist


```shell
curl -X GET \
  https://shoupbud.xyz/api/wishlist \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW'
```

> Resopnse Sukses

```json
{
  "status": "OK",
  "wishlist": [
    {
      "id": 15,
      "user_id": 9,
      "product_id": 15,
      "created_at": "2017-04-25 04:32:51",
      "updated_at": "2017-04-25 04:32:51"
    }
  ],
  "message": null
}
```

## Tambah Produk ke daftar Wishlist

```shell
curl -X POST \
  https://shoupbud.xyz/api/wishlist \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW'
  -F product_id=1

```

> Response Sukses (200)

```json
{
  "status": "OK",
  "wishlist": {
    "product_id": "15",
    "user_id": 9,
    "updated_at": "2017-04-25 04:32:51",
    "created_at": "2017-04-25 04:32:51",
    "id": 15
  },
  "message": null
}
```

> Response Fail (400)

```json
{
  "status": "ERROR",
  "wishlist": null,
  "message": "Data product tidak ditemukan"
}
```

## Hapus Daftar Wishlist


```shell
curl -X DELETE \
  https://shoupbud.xyz/api/wishlist/1 \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' 
```