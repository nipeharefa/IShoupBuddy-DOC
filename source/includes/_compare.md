# Compare

## Get Compare


```shelle
curl -X GET \
  'https://shoupbud.xyz/compare?product_id=38' \
  -H 'accept: application/json'
```

> Response Success (200)

```json
{
    "source": {
        "id": 37,
        "name": "Hit Product",
        "category": {
            "id": 1,
            "name": "Uncategorized",
            "slug": "uncategorized",
            "picture_url": null,
            "description": null
        },
        "barcode": 1234,
        "description": "-123",
        "picture_url": {
            "small": "http://skripsi.home.dev/image/small/WEBg1WgZRPE1v4u5sLbH.jpg",
            "medium": "http://skripsi.home.dev/image/medium/WEBg1WgZRPE1v4u5sLbH.jpg",
            "large": "http://skripsi.home.dev/image/large/WEBg1WgZRPE1v4u5sLbH.jpg"
        },
        "vendors": [],
        "total_review": 0,
        "total_vendor": 0,
        "total_rating": 0,
        "avg_rating": null,
        "minimum_price": null,
        "minimum_price_string": "Rp. 0",
        "minumumPrice": null,
        "liked": false,
        "recentReview": [],
        "summary": {
            "mean": {
                "pos": null,
                "neg": null,
                "neu": null
            },
            "count": {
                "pos": 0,
                "neg": 0,
                "neu": 0
            }
        }
    },
    "target": {
        "id": 38,
        "name": "Hit Aerosol",
        "category": {
            "id": 1,
            "name": "Uncategorized",
            "slug": "uncategorized",
            "picture_url": null,
            "description": null
        },
        "barcode": 111,
        "description": "-1",
        "picture_url": {
            "small": "http://skripsi.home.dev/image/small/lQh2n5kTWKQIMpLz6NFh.jpg",
            "medium": "http://skripsi.home.dev/image/medium/lQh2n5kTWKQIMpLz6NFh.jpg",
            "large": "http://skripsi.home.dev/image/large/lQh2n5kTWKQIMpLz6NFh.jpg"
        },
        "vendors": [],
        "total_review": 0,
        "total_vendor": 0,
        "total_rating": 0,
        "avg_rating": null,
        "minimum_price": null,
        "minimum_price_string": "Rp. 0",
        "minumumPrice": null,
        "liked": false,
        "recentReview": [],
        "summary": {
            "mean": {
                "pos": null,
                "neg": null,
                "neu": null
            },
            "count": {
                "pos": 0,
                "neg": 0,
                "neu": 0
            }
        }
    }
}
```