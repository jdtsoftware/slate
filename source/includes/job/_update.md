## Update a Job

```shell
curl -X POST \
  BASE_URL/admin/api/job/{id}/update \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F job_category=ACCOUNTS_MANAGER \
  -F job_type=perm_fulltime \
  -F reference=12345678955 \
  -F 'name=Job Title' \
  -F 'description=Job Description' \
  -F 'summary=Job Summary' \
  -F open_date=2017-09-01 \
  -F 'premise=Talent on View' \
  -F 'sub_premise=Unit 25' \
  -F 'thoroughfare=The Innovation Centre' \
  -F 'locality=217 Portobello' \
  -F 'main_area=Sheffield' \
  -F 'sub_area=South Yorkshire' \
  -F 'postal_code=S1 4DP' \
  -F country=GB \
  -F 'location_display=Sheffield, United Kingdom' \
  -F show_map=1 \
  -F 'location_geo_lat=53.3811' \
  -F 'location_geo_lon=1.4701' \
  -F salary_frequency=ANNUALLY \
  -F salary_currency=GBP \
  -F salary_to=25000 \
  -F salary_text=Competitive \
  -F apply_type=REDIRECT \
  -F 'apply_data=http://job.com/job/12345678955'
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->post('BASE_URL/admin/api/job/{id}/update', [
    'headers' => [
        'accept' => 'application/vnd.jb.v1+json',
        'authorization' => 'Bearer ACCESS_TOKEN',
    ],
    'form_params' => [
        'job_category' => 'ACCOUNTS_MANAGER',
        'job_type' => 'perm_fulltime',
        'reference' => '12345678955',
        'name' => 'Job Title',
        'description' => 'Job Description',
        'summary' => 'Job Summary',
        'open_date' => '2017-09-01',
        'premise' => 'Talent on View',
        'sub_premise' => 'Unit 25',
        'thoroughfare' => 'The Innovation Centre',
        'locality' => '217 Portobello',
        'main_area' => 'Sheffield',
        'sub_area' => 'South Yorkshire',
        'postal_code' => 'S1 4DP',
        'country' => 'GB',
        'location_display' => 'Sheffield, United Kingdom',
        'show_map' => true,
        'location_geo_lat' => 53.3811,
        'location_geo_lon' => 1.4701,
        'salary_frequency' => 'ANNUALLY',
        'salary_currency' => 'GBP',
        'salary_from' => 25000,
        'salary_to' => 30000,
        'salary_text' => 'Competitive',
        'apply_type' => 'REDIRECT',
        'apply_data' => 'http://job.com/job/12345678955',
    ],
]);

return json_decode((string) $response->getBody(), true);
```

> The above command, on successful creation, returns JSON structured like this:

```json
{
    "data": {
        "links": {
            "self": "BASE_URL/api/job/143"
        },
        "id": 143,
        "reference": "12345678955",
        "slug": "test/143/job-title",
        "number_applied": null,
        "job_title": "Job Title",
        "name": "Job Title",
        "summary": "Job Summary",
        "description": "Job Description",
        "benefits": null,
        "skills": null,
        "content_mode": null,
        "salary_from": null,
        "salary_to": null,
        "salary_text": "Competitive",
        "open_date": {
            "utc": "2017-09-01T00:00:00+00:00",
            "converted": "2017-08-31T20:00:00-04:00",
            "formatted": "31 Aug 2017 20:00:00"
        },
        "close_date": {
            "utc": "2017-09-29T00:00:00+00:00",
            "converted": "2017-09-28T20:00:00-04:00",
            "formatted": "28 Sep 2017 20:00:00"
        },
        "creator_name": "Test Martin",
        "location_display": "Sheffield, United Kingdom",
        "location": {
            "display": "Sheffield, United Kingdom",
            "postcode": 23,
            "country": 229,
            "geo": {
                "lon": -1.4811218976974487,
                "lat": 53.38109588623047
            }
        },
        "created_at": {
            "utc": "2017-09-15T12:23:49+00:00",
            "converted": "2017-09-15T08:23:49-04:00",
            "formatted": "15 Sep 2017 08:23:49"
        },
        "updated_at": {
            "utc": "2017-09-15T12:23:49+00:00",
            "converted": "2017-09-15T08:23:49-04:00",
            "formatted": "15 Sep 2017 08:23:49"
        },
        "deleted_at": null,
        "premise": "Talent on View",
        "sub_premise": "Unit 25",
        "thoroughfare": "The Innovation Centre",
        "locality": "217 Portobello",
        "main_area": "Sheffield",
        "sub_area": "South Yorkshire",
        "country_id": 229,
        "postcode": "S14DP",
        "source_address": "manual",
        "language": {
            "data": {
                "id": 1,
                "iso_code": "en",
                "name": "English"
            }
        },
        "salary_frequency": {
            "data": {
                "id": 7,
                "handle": "ANNUALLY"
            }
        },
        "salary_currency": {
            "data": {
                "id": 4,
                "iso_code": "GBP",
                "symbol": "£",
                "unicode": "&#163;"
            }
        },
        "organisation": {
            "data": {
                "id": 10,
                "handle": "test",
                "name": "Test"
            }
        },
        "address": {
            "data": {
                "id": 45,
                "source_id": 2,
                "postcode_id": 23,
                "premise": "Talent on View",
                "sub_premise": "Unit 25",
                "thoroughfare": "The Innovation Centre",
                "locality": "217 Portobello",
                "geo_lon": -1.4811218976974487,
                "geo_lat": 53.38109588623047,
                "country": {
                    "id": 229,
                    "iso": "GB",
                    "name": "United Kingdom",
                    "geo_lon": 0,
                    "geo_lat": 0
                },
                "administrative": {
                    "id": 2,
                    "source_id": 1,
                    "main_area": "Sheffield",
                    "sub_area": "South Yorkshire",
                    "geo_lon": -1.4811218976974487,
                    "geo_lat": 53.38109588623047,
                    "country": {
                        "id": 229,
                        "iso": "GB",
                        "name": "United Kingdom",
                        "geo_lon": 0,
                        "geo_lat": 0
                    }
                },
                "postcode": {
                    "id": 23,
                    "postcode": "S14DP"
                }
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
      "reference": [
        "The reference field is required."
      ],
      "name": [
        "The name field is required."
      ],
      "description": [
        "The description field is required."
      ],
      "benefits": [
        "The benefits field is required."
      ],
      "skills": [
        "The skills field is required."
      ],
      "open_date": [
        "The open date field is required."
      ]
    },
    "status_code": 422
  }
}
```

> Example Error 402 Response

```json
{
  "data": {
    "message": "Insufficient Credits",
    "status_code": 402
  }
}
```

> Example Error 401 Response

```json
{
  "data": {
    "message": "Unauthenticated",
    "status_code": 401
  }
}
```

This endpoint updates a job.

### HTTP Request

`POST BASE_URL/admin/api/job/{id}/update`

### Query Parameters

Parameter | Required | Validation | Description
--------- | -------- | ---------- | ----------- 
job_category | true | String | Handle from job_category in options lookup.
job_type | true | String | Handle from job_type in options lookup.
reference | true | String, Min 5 characters, Max 191 Characters, Unique to Organisation | The reference for the job.
name | true | String, Min 5 characters, Max 191 Characters | The title of the job.
description | true | String, Min 5 characters, Max 4294967295 Characters | The description of the job.
summary | false | String, Max 300 Characters | This is the summary of the job that will be displayed when searching. If this is left blank the first 300 characters of the description will be used.
open_date | true | YYYY-MM-DD | The date you want the advert to go live.
close_date | false | YYYY-MM-DD | This field is optional if you are unsure leave blank and the system will auto populate. If the expiry date is greater than the contracted length extra tokens maybe deducted.
premise | true | String, Max 191 Characters | Address line 1.
sub_premise | false | String, Max 191 Characters | Address line 2.
thoroughfare | false | String, Max 191 Characters | Address line 3.
locality | false | String, Max 191 Characters | Address line 4.
main_area | true | String, Max 191 Characters | Town / City.
sub_area | true | String, Max 191 Characters | County / State.
postal_code | true | String, Max 191 Characters | Post Code / Zip Code.
country | true | String | Handle from country in options lookup.
location_display | true | String, Max 191 Characters | This is what is shown to the candidate when viewing the job.
show_map | false | Boolean | Should the map be displayed to the candidate. (Default : true).
location_geo_lat | false | Float | The latitude of the job. If not supplied we will geocode automatically from the address.
location_geo_lon | false | Float | The longitude of the job. If not supplied we will geocode automatically from the address.
salary_frequency | true | String | Handle from salary_frequency in options lookup.
salary_currency | true | String | Handle from salary_currency in options lookup.
salary_from | true | Float | The minimum salary for the job.
salary_to | true | Float | The maximum salary for the job.
salary_text | true | Float | What to display to the candidate e.g. Competitive or £20,000 to £30,000.
apply_type | true | String | Handle from apply_type in options lookup.
apply_data | if apply_type = REDIRECT or SIGNUP_WITHPOST | Url, Max 3000 Characters | The url to redirect the candidate when they apply for the job.
apply_data | if apply_type = EMAIL | Email | The email to send candidates to when they apply for the job.

