## Password Grant

The OAuth2 password grant allows your other first-party clients, 
such as a mobile application, to obtain an access token using an 
e-mail address / username and password. This allows you to issue access tokens 
securely to your first-party clients without requiring your users to go through 
the entire OAuth2 authorization code redirect flow.

When using this method The Job Space expects all API requests to the server to include a authorisation bearer token to be in a header that looks like the following:

`Authorization: Bearer OAUTH_ACCESS_TOKEN`

<aside class="notice">
You must replace <code>OAUTH_ACCESS_TOKEN</code> with your access token generated from /oauth/token using your API key.
</aside>

> To authorize, use this code:

> Make sure to replace `BASE_URL`, `CLIENT_ID`, `CLIENT_SECRET`, `USERNAME`, and `PASSWORD` with the credentials given to you.
> CLIENT_ID and CLIENT_SECRET authenticate the vendor while the USERNAME AND PASSWORD allow you to post on behalf of a given user. 

```shell
curl -X POST \
  BASE_URL/oauth/token \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F grant_type=password \
  -F client_id=CLIENT_ID \
  -F client_secret=CLIENT_SECRET \
  -F username=USERNAME \
  -F password=PASSWORD
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->post('BASE_URL/oauth/token', [
    'form_params' => [
        'grant_type' => 'password',
        'client_id' => 'CLIENT_ID',
        'client_secret' => 'CLIENT_SECRET',
        'username' => 'USERNAME',
        'password' => 'PASSWORD',
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
grant_type | password | Which grant type to use. 
client_id | CLIENT_ID | Your api client id. 
client_secret | CLIENT_SECRET | Your api client secret. 
username | USERNAME | The username of the person you want to impersonate. 
password | PASSWORD | The password of the person you want to impersonate. 