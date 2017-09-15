## Refresh Access Token

If the access token has expired you can refresh it without having to worry about getting the users permission.
To use this endpoint you will need to store the refresh token that was returned to you
when getting the access token originally.

> To Refresh, use this code:

> Make sure to replace `BASE_URL`, `CLIENT_ID`, `CLIENT_SECRET` and `REFRESH_TOKEN` with the credentials given to you.
> CLIENT_ID and CLIENT_SECRET authenticate the vendor while the REFRESH_TOKEN is used to give you a new access token. 

```shell
curl -X POST \
  BASE_URL/oauth/token \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F grant_type=refresh_token \
  -F refresh_token=REFRESH_TOKEN \
  -F username=USERNAME \
  -F password=PASSWORD
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->post('BASE_URL/oauth/token', [
    'form_params' => [
        'grant_type' => 'refresh_token',
        'client_id' => 'CLIENT_ID',
        'client_secret' => 'CLIENT_SECRET',
        'refresh_token' => 'REFRESH_TOKEN',
    ],
]);

return json_decode((string) $response->getBody(), true);
```

> The above command returns JSON structured like this:

```json
{
  "token_type": "Bearer",
  "expires_in": 86400,
  "access_token": "a_random_token",
  "refresh_token": "a_refresh_token"
}
```

### HTTP Request

`POST BASE_URL/oauth/token`

### Body

Parameter | Value | Description
--------- | ------- | -----------
grant_type | refresh_token | Which grant type to use. 
client_id | CLIENT_ID | Your api client id. 
client_secret | CLIENT_SECRET | Your api client secret. 
refresh_token | REFRESH_TOKEN | The refresh token given to you when you got the access token. 