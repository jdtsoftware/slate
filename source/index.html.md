---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - php

toc_footers:
  - <a href='mailto:api@thejobspace.com'>Request Developer Key</a>

includes:
  - job/readall
  - job/read
  - job/create
  - job/update
  - lookups/countries
  - lookups/jobtypes
  - lookups/jobcategories
  - errors
  

search: true
---

# Introduction

Welcome to The Job Space API! 

You can use our API to access Job and Application API endpoints, which can get information on jobs, applicants, as well as everything else.


# Authentication

> To authorize, use this code:

> Make sure to replace `CLIENT_ID` and `CLIENT_SECRET` with the credentials given to you.

```ruby
require 'uri'
require 'net/http'

url = URI("https://www.thejobspace.com/oauth/token")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["accept"] = 'application/vnd.jb.v1+json'
request.body = "------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"grant_type\"\r\n\r\nclient_credentials\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_id\"\r\n\r\nCLIENT_ID\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_secret\"\r\n\r\nCLIENT_SECRET\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW--"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://www.thejobspace.com/oauth/token"

payload = "------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"grant_type\"\r\n\r\nclient_credentials\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_id\"\r\n\r\nCLIENT_ID\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_secret\"\r\n\r\nCLIENT_SECRET\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW--"
headers = {
    'accept': "application/vnd.jb.v1+json",
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl -X POST \
  https://www.thejobspace.com/oauth/token \
  -H 'accept: application/vnd.jb.v1+json' \
  -F grant_type=client_credentials \
  -F client_id=CLIENT_ID \
  -F client_secret=CLIENT_SECRET
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://www.thejobspace.com/oauth/token');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'accept' => 'application/vnd.jb.v1+json',
));

$request->setBody('------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="grant_type"

client_credentials
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="client_id"

CLIENT_ID
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="client_secret"

CLIENT_SECRET
------WebKitFormBoundary7MA4YWxkTrZu0gW--');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above command returns JSON structured like this:

```json
{
  "token_type": "Bearer",
  "expires_in": 86400,
  "access_token": "a_random_token"
}
```


The Job Space uses API keys to allow access to the API. You can request new API key by emailing us api@thejobspace.com.

The Job Space expects all API requests to the server to include a authorisation bearer token to be in a header that looks like the following:

`Authorization: Bearer OAUTH_ACCESS_TOKEN`

<aside class="notice">
You must replace <code>OAUTH_ACCESS_TOKEN</code> with your access token genreated from /oauth/token using your API key.
</aside>
