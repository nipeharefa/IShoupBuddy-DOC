# User

## Get User Info

## Get User Account Settings

<aside class="notice">
Requires authentication.
</aside>
## Change Password


```shell
curl -X POST \
  https://shoupbud.xyz/api/user/change_password \
    -H 'accept: application/json' \
    -H 'authorization: Bearer token \
    -F current_password=nipeharefa \
    -F password=nipeharefa \
    -F password_confirmation=nipeharefa
```

> Response Sukses (200)

```json
{
    "status": "OK",
    "message": "Password berhasil dipeerbaharui"
}
```

> Response Fail (400)

```json
{
    "status": "ERROR",
    "message": "Current password error"
}
```

## Update User Account Settings

<aside class="notice">
Requires authentication.
</aside>

Parameter | | Description
--------- | --------- | -----------
`name` | required | User's name
`gender` | required | User's gender
`picture_url` | 'filename|blob' required | User's picture
`address` | required | User's Address
`phone` | required | User's phone


```shell
curl -X POST \
  https://shoupbud.xyz/api/user/ \
  -H 'accept: application/json' \
  -H 'authorization: Bearer token' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/x-www-form-urlencoded' \
  -F name=Nipe \
  -F gender=1 \
  -F address=Medan \
  -F 'picture_url=@Screenshot from 2017-04-18 15:00:18.png'
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