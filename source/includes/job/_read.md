## Read a Job

```shell
curl -X GET \
  BASE_URL/api/job/142 \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->get('BASE_URL/api/job/142', [
    'headers' => [
        'accept' => 'application/vnd.jb.v1+json',
        'authorization' => 'Bearer ACCESS_TOKEN',
    ],
]);

return json_decode((string) $response->getBody(), true);
```

> The above command returns JSON structured like this:

```json
{
   "data":{
      "links":{
         "self":"BASE_URL/api/job/142",
         "apply":"BASE_URL/api/job/142/apply"
      },
      "id":142,
      "reference":"1234567893",
      "slug":"test/142/php-developer",
      "number_applied":0,
      "job_title":"PHP Developer",
      "name":"PHP Developer",
      "summary":"Lamp Developer",
      "description":"All of the skills",
      "benefits":null,
      "skills":null,
      "content_mode":"html",
      "salary_from":"0.00",
      "salary_to":"0.00",
      "salary_text":"Competitive",
      "open_date":{
         "utc":"2017-09-14T00:00:00+00:00",
         "converted":"2017-09-13T20:00:00-04:00",
         "formatted":"13 Sep 2017 20:00:00"
      },
      "close_date":{
         "utc":"2017-10-14T00:00:00+00:00",
         "converted":"2017-10-13T20:00:00-04:00",
         "formatted":"13 Oct 2017 20:00:00"
      },
      "creator_name":"Test Martin",
      "location_display":"Sheffield, South Yorkshire",
      "location":{
         "display":"Sheffield, South Yorkshire",
         "postcode":22,
         "country":229,
         "geo":{
            "lon":"-1.419806718826294",
            "lat":"53.39396667480469"
         }
      },
      "apply_type":"SIGNUP",
      "apply_data":null,
      "created_at":{
         "utc":"2017-09-14T09:57:47+00:00",
         "converted":"2017-09-14T05:57:47-04:00",
         "formatted":"14 Sep 2017 05:57:47"
      },
      "updated_at":{
         "utc":"2017-09-14T09:57:47+00:00",
         "converted":"2017-09-14T05:57:47-04:00",
         "formatted":"14 Sep 2017 05:57:47"
      },
      "deleted_at":null,
      "premise":"123 Main Road",
      "sub_premise":null,
      "thoroughfare":"",
      "locality":null,
      "main_area":"Sheffield",
      "sub_area":"South Yorkshire",
      "country_id":229,
      "postcode":"S21123",
      "source_address":"manual",
      "language":{
         "data":{
            "id":1,
            "iso_code":"en",
            "name":"English"
         }
      },
      "salary_frequency":{
         "data":{
            "id":7,
            "handle":"ANNUALLY"
         }
      },
      "salary_currency":{
         "data":{
            "id":4,
            "iso_code":"GBP",
            "symbol":"£",
            "unicode":"&#163;"
         }
      },
      "organisation":{
         "data":{
            "id":10,
            "handle":"test",
            "name":"Test",
            "description":null,
            "created_at":{
               "utc":"2017-09-11T22:14:08+00:00",
               "converted":"2017-09-11T18:14:08-04:00",
               "formatted":"11 Sep 2017 18:14:08"
            },
            "updated_at":{
               "utc":"2017-09-11T22:14:08+00:00",
               "converted":"2017-09-11T18:14:08-04:00",
               "formatted":"11 Sep 2017 18:14:08"
            },
            "deleted_at":null
         }
      },
      "address":{
         "data":{
            "id":16,
            "source_id":2,
            "postcode_id":22,
            "premise":"123 Main Road",
            "sub_premise":null,
            "thoroughfare":"",
            "locality":null,
            "geo_lon":-1.419806718826294,
            "geo_lat":53.39396667480469,
            "country":{
               "id":229,
               "iso":"GB",
               "name":"United Kingdom",
               "geo_lon":0,
               "geo_lat":0
            },
            "administrative":{
               "id":2,
               "source_id":1,
               "main_area":"Sheffield",
               "sub_area":"South Yorkshire",
               "geo_lon":-1.4811218976974487,
               "geo_lat":53.38109588623047,
               "country":{
                  "id":229,
                  "iso":"GB",
                  "name":"United Kingdom",
                  "geo_lon":0,
                  "geo_lat":0
               }
            },
            "postcode":{
               "id":22,
               "postcode":"S21123"
            }
         }
      }
   },
   "meta":{
      "similarity_boxes":[
         {
            "handle":"MORE_LIKE_THIS",
            "data":[

            ]
         }
      ]
   }
}
```

This endpoint retrieves a single job.

### HTTP Request

`GET BASE_URL/api/job/142`

### Headers

Parameter | Value | Description
--------- | ------- | -----------
Accept | application/vnd.jb.v1+json | The API version you want to access. 
Authorization | BEARER ACCESS_TOKEN | The access token from authorisation section