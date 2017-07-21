# Saldo


## Tambah Nominal Saldo


| Name    |                  | Description         |
|---------|------------------|---------------------|
| nominal | required,integer | Nominal topup saldo |



```shell
curl -X POST \
  https://shoupbud.xyz/api/saldo \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -F nominal=100000
```

> Response Sukses

```json
{
  "status": "OK",
  "message": null,
  "saldo": {
    "id": 52,
    "status": false,
    "nominal": 100093,
    "issueDate": "2017-06-04T14:33:03+00:00"
  }
}
```


## Get Saldo

```shell
curl -X GET \
  https://shoupbud.xyz/api/saldo \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
```

```json
{
  "message": "",
  "saldo": 100093,
  "history": [
    {
      "id": 52,
      "nominal": 100093,
      "nominal_string": "Rp. 100.093",
      "user": {
        "id": 45,
        "name": "Nipe Harefa Test Other User",
        "picture_url": "TO7eS8cBvo6wsUxF9PNd.jpg"
      },
      "type": "Saldo",
      "status": 0,
      "status_string": "Pending",
      "updated_at": "2017-06-04T14:33:03+00:00",
      "links": {
        "approve": "/api/admin/transaction/52/approve",
        "cancel": "/api/admin/transaction/52/cancel"
      }
    }
  ],
  "status": "OK"
}
```

## Upload Attachment

| name  |      | Description |
|-------|------|-------------|
| image | file | Image       |


```sh
curl -X POST \
  http://localhost:3000/api/transaction/8/upload \
  -H 'accept: application/json' \
  -H 'authorization: token' \
  -F image=@ycuOT5oO2r5BSe8RsRkE.jpg
```

```json
{
    "transaction": {
        "id": 8,
        "nominal": 10067,
        "nominal_string": "Rp. 10.067",
        "user": {
            ...
        },
        "type": "Saldo",
        "status": 3,
        "status_string": "Attachment Uploaded",
        "updated_at": "2017-07-21T10:49:34+07:00",
        ...
        "shipment": null,
        "attachments": {
            "small": "http://skripsi.home.dev/image/small/8_1500608974.jpg",
            "medium": "http://skripsi.home.dev/image/medium/8_1500608974.jpg",
            "large": "http://skripsi.home.dev/image/large/8_1500608974.jpg"
        }
    }
}
```