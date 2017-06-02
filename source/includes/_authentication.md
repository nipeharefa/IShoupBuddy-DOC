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
  "access_token": "eyJ0eXAiOiJKV1QiLCJh.....",
  "refresh_token": "r8b7R+SflHsagfhvrtQoDv....
}
```