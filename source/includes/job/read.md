## Read a Job

```ruby
require 'uri'
require 'net/http'

url = URI("https://beta.thejobspace.com/api/job/1234")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/vnd.jb.v1+json'
request["authorization"] = 'Bearer ACCESS_TOKEN'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("www.thejobspace.com")

headers = {
    'accept': "application/vnd.jb.v1+json",
    'authorization': "Bearer ACCESS_TOKEN"
    }

conn.request("GET", "/api/job/1234", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```shell
curl -X GET \
  https://www.thejobspace.com/api/job/1234 \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://www.thejobspace.com/api/job/1234');
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
  "data":
    {
      "id": 1234,
      "reference": "JDT/UK/1234",
      "number_applied": 0,
      "job_title": "Digital Communications Executive",
      "job_title_suggest": {
        "input": [
          "Digital Communications Executive"
        ],
        "output": "Digital Communications Executive",
        "payload": {
          "id": 1234
        },
        "context": {
          "location": {
            "lat": "51.2010517",
            "lon": "-0.4158124"
          }
        }
      },
      "slug": "jdt/1234/digital-communications-executive",
      "summary": "Short summary of job",
      "description": "Description of job",
      "benefits": "Competitve",
      "skills": "All the skills.",
      "salary": {
        "from": "30000.00",
        "to": "39999.00",
        "text": "Competitive",
        "frequency": "ANNUALLY",
        "currency": {
          "iso_code": "",
          "symbol": "",
          "unicode": ""
        }
      },
      "location": {
        "display": "Sutton, Surrey",
        "postcode": {
          "id": 834,
          "postcode": "SM14LD"
        },
        "country": {
          "id": 229,
          "iso": "GB",
          "name": "United Kingdom",
          "geo": {
            "lon": 0,
            "lat": 0
          }
        },
        "geo": {
          "lon": "-0.4158124",
          "lat": "51.2010517"
        }
      },
      "language": {
        "data": {
          "id": 1,
          "iso_code": "en",
          "name": "English"
        }
      },
      "open_date": {
        "utc": "2017-04-27T00:00:00+00:00",
        "converted": "2017-04-26T20:00:00-04:00",
        "formatted": "26 Apr 2017 20:00:00"
      },
      "close_date": {
        "utc": "2017-05-18T00:00:00+00:00",
        "converted": "2017-05-17T20:00:00-04:00",
        "formatted": "17 May 2017 20:00:00"
      },
      "created_at": {
        "utc": "2017-04-06T06:00:15+00:00",
        "converted": "2017-04-06T02:00:15-04:00",
        "formatted": "6 Apr 2017 02:00:15"
      },
      "updated_at": {
        "utc": "2017-04-27T14:47:49+00:00",
        "converted": "2017-04-27T10:47:49-04:00",
        "formatted": "27 Apr 2017 10:47:49"
      },
      "deleted_at": null,
      "category": {
        "data": {
          "id": 604,
          "handle": "INTERNAL_COMMUNICATIONS",
          "parent": {
            "id": 138,
            "handle": "MARKETING_PR"
          }
        }
      },
      "type": {
        "data": {
          "id": 1,
          "handle": "perm_fulltime"
        }
      },
      "media": {
        "data": [
          {
            "id": 6,
            "type": "JOB_LOGO",
            "path": "https://www.thejobspace.com/img/the-job-space/logo-min.png"
          }
        ]
      },
      "address": null,
      "links": {
        "self": "https://www.thejobspace.com/api/job/1234",
        "apply": "https://www.thejobspace.com/api/job/1234/apply"
      }
    }
  }
}
```

This endpoint retrieves a single job.

### HTTP Request

`GET https://www.thejobspace.com/api/job/1234`

### Headers

Parameter | Value | Description
--------- | ------- | -----------
Accept | application/vnd.jb.v1+json | The API version you want to access. 
Authorization | BEARER ACCESS_TOKEN | The access token from authorisation section

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Page number 
page[size] | 25 | The number of items returned per page