## Job Types

> Make sure to replace `ACCESS_TOKEN` with the access token given to you from the authorisation section.

```ruby
require 'uri'
require 'net/http'

url = URI("http://www.thejobspace.com/api/job/type")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/vnd.jb.v1+json'
request["authorization"] = 'Bearer ACCESS_TOKEN'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPConnection("www.thejobspace.com")

headers = {
    'accept': "application/vnd.jb.v1+json",
    'authorization': "Bearer ACCESS_TOKEN",
    'cache-control': "no-cache",
    'postman-token': "6c42a589-4760-7250-2d2f-135bf1885366"
    }

conn.request("GET", "/api/job/type", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```shell
curl -X GET \
  http://www.thejobspace.com/api/job/type \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN'
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://www.thejobspace.com/api/job/type');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'authorization' => 'Bearer ACCESS_TOKEN',
  'accept' => 'application/vnd.jb.v1+json'
));

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
  "data": [
    {
      "id": 1,
      "handle": "perm_fulltime",
      "created_at": {
        "utc": "2016-10-30T21:25:27+00:00",
        "converted": "2016-10-30T17:25:27-04:00",
        "formatted": "30 Oct 2016 17:25:27"
      },
      "updated_at": {
        "utc": "2016-10-30T21:25:27+00:00",
        "converted": "2016-10-30T17:25:27-04:00",
        "formatted": "30 Oct 2016 17:25:27"
      }
    },
    {
      "id": 2,
      "handle": "perm_parttime",
      "created_at": {
        "utc": "2016-10-30T21:25:27+00:00",
        "converted": "2016-10-30T17:25:27-04:00",
        "formatted": "30 Oct 2016 17:25:27"
      },
      "updated_at": {
        "utc": "2016-10-30T21:25:27+00:00",
        "converted": "2016-10-30T17:25:27-04:00",
        "formatted": "30 Oct 2016 17:25:27"
      }
    }
  ]
}
```

This endpoint retrieves all jobs.

### HTTP Request

`GET https://www.thejobspace.com/api/job/type`

### Headers

Parameter | Value | Description
--------- | ------- | -----------
Accept | application/vnd.jb.v1+json | The API version you want to access. 
Authorization | BEARER ACCESS_TOKEN | The access token from authorisation section

