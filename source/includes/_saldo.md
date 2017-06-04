# Saldo


## Tambah Nominal Saldo


| Name    |                  | Description         |
|---------|------------------|---------------------|
| nominal | required,integer | Nominal topup saldo |



```shell
curl -X POST \
  http://skripsi.home.dev/api/saldo \
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
  http://skripsi.home.dev/api/saldo \
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