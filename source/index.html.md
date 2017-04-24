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


`POST http://shoupbud.xyz/oauth/register/`

### URL Parameters

Parameter | Description
--------- | -----------
name | Your Name
phone | Your Phone
email | Use your email address
password | Your Password


```shell
curl -X POST \
  http://shoupbud.xyz/api/oauth/register \
  -H 'accept: application/json' \
  -F 'name=Your Name' \
  -F email=yourmail@domain \
  -F password=yourpassword \
  -F phone=youremail
```


## Login

### HTTP Request

`POST http://shoupbud.xyz/oauth/login/`

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
  https://shoupbud.xyz/oauth/login \
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