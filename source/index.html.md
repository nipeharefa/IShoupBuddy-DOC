---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the IShoupBud API! This is a Final Assigment;.


# Authentication

## Register


`POST https://shoupbud.xyz/api/oauth/register/`

### URL Parameters

Parameter | Description
--------- | -----------
name | Your Name
phone | Your Phone Number
email | Use your email address
password | Your Password


```shell
curl -X POST \
  https://shoupbud.xyz/api/oauth/register \
  -H 'accept: application/json' \
  -F 'name=Your Name' \
  -F email=yourmail@domain \
  -F password=yourpassword \
  -F phone=youremail
```


## Login

### HTTP Request

`POST https://shoupbud.xyz/api/oauth/login/`

### URL Parameters

Parameter | Description
--------- | -----------
grant_type | Grant Type default
client_id | Client ID from server
client_secret | Client Secret From Server
username | Use your email address
password | Your Password

```shell
curl -X POST \
  https://shoupbud.xyz/api/oauth/login \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -F grant_type=password \
  -F client_id=client_id \
  -F client_secret=client_secret \
  -F username=yourmail@gmail.com \
  -F password=yourpassword
```

```shell
  Response Success
```

```json
{
  "token_type": "Bearer",
  "expires_in": 31536000,
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImFkOGJjZmEyNjM5YTVhNjAxNmYwZTkwNTI1YmQ1MDJmZjk1ZjFkNmE0YWI2NTdiODc1YTVkOGFmNmYxZTdiNTgwMTg2N2U0ZjM0YzNkZTNlIn0.eyJhdWQiOiIyIiwianRpIjoiYWQ4YmNmYTI2MzlhNWE2MDE2ZjBlOTA1MjViZDUwMmZmOTVmMWQ2YTRhYjY1N2I4NzVhNWQ4YWY2ZjFlN2I1ODAxODY3ZTRmMzRjM2RlM2UiLCJpYXQiOjE0OTE4ODcwODUsIm5iZiI6MTQ5MTg4NzA4NSwiZXhwIjoxNTIzNDIzMDg1LCJzdWIiOiI1Iiwic2NvcGVzIjpbXX0.v-jinD6kNI4SKnshrijlCnKB7GPGmp2ATeCsBonDFRu9TVc43GgOrCVunYGcapjTBK6fF-gLmSuHquAXQsf8nSw3IAzNj9V-wRpmZ3GjVjNoV2aNWYYd_C3jzb4ISye2reFWppWwvpmyxkwz-XZI4x233-gJKVzd2hhBk_0i1bPOrEdqZ0rqZjIqxJql-HbHttLlBAcz1rpODXa6JZZbn5gWzCKrNbw3tuKks4d2oW8bAmB1uYsSZmdbEeVVytpIoKTIwauAQglZ2cCI5P6qZIoshNr0wrHRHM5M-g5xX3VuPt7OfT3cI8l7s3lHQibpbhOwTpZt8A00irhWoWK2pVTTkMh9zNnYBkwbnYaeOfm0pWdEbUDmW73A4Znv17yg87W8NOCW9SmEXwPw3w0hGHFH72jtQwcLGXqCFj1ktAVmBqq4HU0ARGyrkvqHbcFZTX4-fi9e40AWKOpYmklDJi_dzWbYYFd8ldW7MrSPCqT8RKLudVgiVjR6nIj9BcIKOI7G7n9iT15s5fTELbOg80x-JL4fM5pFADEtw_VgF3JBE9-mLP-SZy5bV66zUbksExRXqYOSV7JQxc5pacoeOZWaT0s42V0edzBR8xnied8sROPGKpl2ZJTwN-cqlHILyaFwrrzIWDGN9-FWbDZ6UWZY3B8RwRamzaV0Qjhys2U",
  "refresh_token": "r8b7R+SflHsagfhvrtQoDvaHQxHwTWl4RbKid5SfJOiQE0DuHgCYA5goSwUehxpV+GMZfhauMWuuW9BwpfGH1/lt6ygr+yD7D/qWcoBMmk7XbR3NHKWNVhmjHkjYhDMFMpLaJpP0M8ykep9Nd0EXsDU+yd+MxDHSHYr3nQIjkPNzfP0FHFHvYyjxROq9aH6mpRSh7q09UzHER+1aeA+ObumKtnCulDLEmM4CPgDz4QZiK4iqJkzIZZMce+p3rX1OrI4LOx71DC2Yq9EIze8NyygxtHe12jAsb973zHnV28aa6Qe/lTEsMWRzP5BDMU2hCiVRqktYFvRau9UBzxrdpD3n3Pbvx8NYch6QmS1SS2dZsayAHzSkeYoATz5p4lvCGvQ6/AacjHVepvKeRv981k/NfQDbcpEFCRJd0A+T98r1cLiWDBJdnzrskr1WZc3JIHCm66CgiD4nFnep/GM4Z9rQWdjTbLmyRbKl/2XJIPwI5QuNtEvUe0weqdtfxGK9Ikmdo7tNzFCKdZDtbHRdy4bKhSRP478OayiE9WM5aHYescHlbEPIEtN0Cd8RubHHiTFu2GXyzU8gHH+cjn1TYTMtJVhuyOwsbqANu21fIFAWm1AzP7ib6IZeWCHKlvUuEoTIS1y8FeyTwlRm4a9J6Lo74ECsB4I0vi0w0gU6MBg="
}
```

# Category

## Get List Category


```shell
curl -X GET \
  http://skripsi.home.dev/api/category \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache'
```

> Response Success (200)

```json
[
  {
    "id": 1,
    "name": "Uncategorized",
    "slug": "uncategorized",
    "description": null
  }
]
```



# Product

## Get List Produk

Untuk mendapatkan daftar produk yang terdaftar di database tanpa parameter. Jika tedapat parameter tambahan seperti `keyword` maka response akan disesuaikan dengan value dari parameter, dan dapat menggunakan lebih dari satu parameter.  


Parameter | Description
--------- | -----------
`keyword` | Hanya menampilkan produk sesuai dengan keywor
`category_id` | Hanya menampilkan produk dengan kategori tertentu

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


# User

## Get User Info

## Get User Account Settings

<aside class="notice">
Requires authentication.
</aside>

## Update User Account Settings

<aside class="notice">
Requires authentication.
</aside>

Parameter | | Description
--------- | --------- | -----------
`name` | required | User's name
`gender` | required | User's gender

```shell
curl -X PUT \
  https://shoupbud.xyz/api/user/9 \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'name=Nipe%20Setiawan&gender=0'
```


> Response Sukses (200)

```json
{
  "status": "OK",
  "user": {
    "id": 9,
    "name": "Nipe Setiawan",
    "email": "nipeharefa@gmail.com",
    "phone": "082275121178",
    "picture_url": null,
    "role": 1,
    "confirmed": 1,
    "langitude": null,
    "longitude": null,
    "saldo": 0,
    "created_at": "2017-04-23 13:18:12",
    "updated_at": "2017-04-25 07:00:45"
  },
  "message": "Akun telah di update"
}
```

> Error Validasi (422)

```json
{
  "name": [
    "The name field is required."
  ],
  "gender": [
    "The gender field is required."
  ]
}
```


# Vendor

## Get List Vendor


```shell
curl -X GET \
  http://skripsi.home.dev/api/vendor \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'postman-token: df638be6-9162-7912-fa27-715af79bcbb6'
```


> Response Success (200)

```json
{
  "status": "OK",
  "vendors": [
    {
      "id": 44,
      "name": "PT. Alfamart Indonesia",
      "email": "info@alfamart.com",
      "phone": "6282229111",
      "picture_url": null,
      "langitude": null,
      "longitude": null,

    }
  ],
  "message": null
}
```