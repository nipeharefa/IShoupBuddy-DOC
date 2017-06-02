
# Image


## Image Uploader



```shell
curl -X POST \
  https://shoupbud.xyz/api/image \
    -H 'cache-control: no-cache' \
    -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
    -F image=@foto0900.jpg
```

> Response Sukses (200)

```json
{
    "status": "OK",
    "image": "qiirKFHl5spi4k48w5WE.jpg",
    "links": {
        "small": "https://shoupbud.xyz/image/small/qiirKFHl5spi4k48w5WE.jpg",
        "medium": "https://shoupbud.xyz/image/medium/qiirKFHl5spi4k48w5WE.jpg",
        "large": "https://shoupbud.xyz/image/large/qiirKFHl5spi4k48w5WE.jpg"
    },
    "message": null
}
```