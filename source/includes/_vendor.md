# Vendor

## Get List Vendor


```shell
curl -X GET \
  https://shoupbud.xyz/api/vendor \
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