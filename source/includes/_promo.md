# Promo

## Get Promo

```shell
curl -X GET \
  https://shoupbud.xyz/api/promo \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'postman-token: 7a08dfd3-e60c-2103-4f40-4ee831f55133'
```

> Response Sukses (200)

```json
{
  "status": "OK",
  "promo": [
    {
      "id": 24,
      "name": "Soffel Kulit Jeruk 80g",
      "category": {
        "id": 1,
        "name": "Uncategorized",
        "slug": "uncategorized",
        "description": null
      },
      "barcode": 8992772315128,
      "picture_url": {
        "small": "https://shoupbud.xyz/image/small/ce7NxJ8vBdTEHcGMMuif.jpg",
        "medium": "https://shoupbud.xyz/image/medium/ce7NxJ8vBdTEHcGMMuif.jpg",
        "large": "https://shoupbud.xyz/image/large/ce7NxJ8vBdTEHcGMMuif.jpg"
      },
      "description": "",
      "vendors": [
        {
          "id": 2,
          "name": "Soffel Kulit Jeruk 80g",
          "price": 100000,
          "price_string": 100000,
          "barcode": "8992772315128",
          "vendor": {
            "id": 44,
            "name": "PT. Alfamart Indonesia",
            "picture_url": null,
            "total_product": 1,
            "total_review": 0
          }
        }
      ],
      "total_review": 0,
      "total_vendor": 1,
      "total_rating": 0,
      "minimum_price": 100000
    }
  ],
  "message": null
}
```