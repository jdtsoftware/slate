---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - php

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to The Job Space API! 

You can use our API to access Job and Application API endpoints, which can get information on jobs, applicants, as well as everything else.


# Authentication

> To authorize, use this code:

```ruby
require 'uri'
require 'net/http'

url = URI("https://www.thejobspace.com/oauth/token")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["accept"] = 'application/vnd.jb.v1+json'
request["postman-token"] = '0623c0c7-3b02-247c-bce7-07e1d60cb476'
request.body = "------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"grant_type\"\r\n\r\nclient_credentials\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_id\"\r\n\r\n3\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_secret\"\r\n\r\nDSjGyNpJBMza03QfknHHUFW3T4f3NPT3ruuSjqjK\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW--"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://www.thejobspace.com/oauth/token"

payload = "------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"grant_type\"\r\n\r\nclient_credentials\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_id\"\r\n\r\n3\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"client_secret\"\r\n\r\nDSjGyNpJBMza03QfknHHUFW3T4f3NPT3ruuSjqjK\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW--"
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

3
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="client_secret"

DSjGyNpJBMza03QfknHHUFW3T4f3NPT3ruuSjqjK
------WebKitFormBoundary7MA4YWxkTrZu0gW--');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> Make sure to replace `CLIENT_ID` and `CLIENT_SECRET` with the credentials given to you.

The Job Space uses API keys to allow access to the API. You can request new API key by emailing us api@thejobspace.com.

The Job Space expects all API requests to the server to include a authorisation bearer token to be in a header that looks like the following:

`Authorization: Bearer OAUTH_ACCESS_TOKEN`

<aside class="notice">
You must replace <code>OAUTH_ACCESS_TOKEN</code> with your access token genreated from /oauth/token using your API key.
</aside>

# Job

## Get All Jobs

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

