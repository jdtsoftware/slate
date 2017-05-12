## Update a Job

```ruby
require 'uri'
require 'net/http'

url = URI("https://www.thejobspace.com/api/job/{id}/update")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW'
request["accept"] = 'application/vnd.jb.v1+json'
request["authorization"] = 'Bearer ACCESS_TOKEN'
request.body = "------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"organisation\"\r\n\r\nJDT\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"job_category_id\"\r\n\r\n1\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"job_type_id\"\r\n\r\n1\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"reference\"\r\n\r\nJDT/1234\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"name\"\r\n\r\nJob Title\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"description\"\r\n\r\nThe jobs description\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"benefits\"\r\n\r\nBenefits\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"skills\"\r\n\r\nSkills\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"open_date\"\r\n\r\n01-12-2017\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"close_date\"\r\n\r\n01-02-2018\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"country_id\"\r\n\r\n229\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"premise\"\r\n\r\n1 Example Road\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sub_premise\"\r\n\r\nExample Area\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"main_area\"\r\n\r\nSheffield\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sub_area\"\r\n\r\nSouth Yorkshire\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"postcode\"\r\n\r\nS1 4BY\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"location_display\"\r\n\r\nSheffield, South Yorkshire\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_frequency\"\r\n\r\nHOURLY\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_currency\"\r\n\r\nGBP\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_from\"\r\n\r\n10\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_to\"\r\n\r\n10\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_text\"\r\n\r\nCompetitive\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"apply_type\"\r\n\r\nSIGNUP\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sites[]\"\r\n\r\n1\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sites[]\"\r\n\r\n2\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW--"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("www.thejobspace.com")

payload = "------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"organisation\"\r\n\r\nJDT\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"job_category_id\"\r\n\r\n1\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"job_type_id\"\r\n\r\n1\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"reference\"\r\n\r\nJDT/1234\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"name\"\r\n\r\nJob Title\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"description\"\r\n\r\nThe jobs description\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"benefits\"\r\n\r\nBenefits\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"skills\"\r\n\r\nSkills\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"open_date\"\r\n\r\n01-12-2017\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"close_date\"\r\n\r\n01-02-2018\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"country_id\"\r\n\r\n229\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"premise\"\r\n\r\n1 Example Road\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sub_premise\"\r\n\r\nExample Area\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"main_area\"\r\n\r\nSheffield\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sub_area\"\r\n\r\nSouth Yorkshire\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"postcode\"\r\n\r\nS1 4BY\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"location_display\"\r\n\r\nSheffield, South Yorkshire\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_frequency\"\r\n\r\nHOURLY\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_currency\"\r\n\r\nGBP\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_from\"\r\n\r\n10\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_to\"\r\n\r\n10\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"salary_text\"\r\n\r\nCompetitive\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"apply_type\"\r\n\r\nSIGNUP\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sites[]\"\r\n\r\n1\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW\r\nContent-Disposition: form-data; name=\"sites[]\"\r\n\r\n2\r\n------WebKitFormBoundary7MA4YWxkTrZu0gW--"

headers = {
    'content-type': "multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW",
    'accept': "application/vnd.jb.v1+json",
    'authorization': "Bearer ACCESS_TOKEN",
    }

conn.request("POST", "/api/job/{id}/update", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```shell
curl -X POST \
  https://www.thejobspace.com//api/job/{id}/update \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F organisation=JDT \
  -F job_category_id=1 \
  -F job_type_id=1 \
  -F reference=JDT/1234 \
  -F 'name=Job Title' \
  -F 'description=The jobs description' \
  -F benefits=Benefits \
  -F skills=Skills \
  -F open_date=01-12-2017 \
  -F close_date=01-02-2018 \
  -F country_id=229 \
  -F 'premise=1 Example Road' \
  -F 'sub_premise=Example Area' \
  -F main_area=Sheffield \
  -F 'sub_area=South Yorkshire' \
  -F 'postcode=S1 4BY' \
  -F 'location_display=Sheffield, South Yorkshire' \
  -F salary_frequency=HOURLY \
  -F salary_currency=GBP \
  -F salary_from=10 \
  -F salary_to=10 \
  -F salary_text=Competitive \
  -F apply_type=SIGNUP \
  -F 'sites[]=1' \
  -F 'sites[]=2'
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://www.thejobspace.com/api/job/{id}/update');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'authorization' => 'Bearer ACCESS_TOKEN',
  'accept' => 'application/vnd.jb.v1+json',
  'content-type' => 'multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW'
));

$request->setBody('------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="organisation"

JDT
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="job_category_id"

1
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="job_type_id"

1
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="reference"

JDT/1234
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="name"

Job Title
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="description"

The jobs description
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="benefits"

Benefits
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="skills"

Skills
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="open_date"

01-12-2017
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="close_date"

01-02-2018
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="country_id"

229
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="premise"

1 Example Road
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="sub_premise"

Example Area
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="main_area"

Sheffield
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="sub_area"

South Yorkshire
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="postcode"

S1 4BY
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="location_display"

Sheffield, South Yorkshire
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="salary_frequency"

HOURLY
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="salary_currency"

GBP
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="salary_from"

10
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="salary_to"

10
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="salary_text"

Competitive
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="apply_type"

SIGNUP
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="sites[]"

1
------WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="sites[]"

2
------WebKitFormBoundary7MA4YWxkTrZu0gW--');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above command, on successful creation, returns JSON structured like this:

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

> Example Error 422 Response

```json
{
  "data": {
    "message": "422 Unprocessable Entity",
    "errors": {
      "organisation": [
        "The organisation field is required.",
      ],
      "reference": [
        "The reference field is required.",
      ],
      "name": [
        "The name field is required.",
      ],
      "description": [
        "The description field is required.",
      ],
      "benefits": [
        "The benefits field is required.",
      ],
      "skills": [
        "The skills field is required.",
      ],
      "open_date": [
        "The open date field is required.",
      ],
      "close_date": [
        "The close date field is required.",
      ]
    },
    "status_code": 422
  }
}
```

This endpoint updates a job.

### HTTP Request

`POST https://www.thejobspace.com/api/job/{id}/update`

### Query Parameters

Parameter | Required | Description
--------- | ------- | ----------- 
organisation | true | String (A valid list will be provided with your Client ID and Client Secret)
job_category_id | true | Integer - See Look Ups > Job Categories  
job_type_id | true | Integer - See Look Ups > Job Types
reference | true | Job Reference Max 255
name | true | String Max 255
description | true | String Max 6500 characters
benefits | true | String Max 6500 characters
skills | true | String Max 6500 characters
open_date | true | Date in format 30-12-2017
close_date | true | Date in format 30-12-2017 
country_id | true | Integer - See Look Ups > Countries 
premise | true | String Max 255
thoroughfare | true | String Max 255 
locality | true | String Max 255
postal_code | true | String Max 255
main_area | true | String Max 255
salary_frequency | true | String - See Salary Frequency Types table below  
salary_currency | true | String - ISO 4217 currency codes 
salary_text | true | String Max 255
apply_type | true | String - See Apply Type table below
apply_url | optional | Required if apply_type is REDIRECT 
sites | true | Array of Integers (A valid list will be provided with your Client ID and Client Secret)

### Reference Tables 

### Apply Types 
Handle | Description
--------- | -------
REDIRECT | When the candidate applies they will be redirected to the URL given in apply_url parameter
SIGNUP | When the candidate applies they will be managed from within The Job Space

### Salary Frequency Types 
Handle | Description
--------- | -------
HOURLY | Paid per Hourly
DAILY | Paid Daily
WEEKLY | Page weekly 
FORTNIGHTLY | Paid fortnightly 
4WEEKLY | Paid every 4 weeks 
MONTHLY | Paid monthly 
ANNUALLY | Paid annually 
