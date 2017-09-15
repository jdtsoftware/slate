# Job 

## Read all jobs

> Make sure to replace `ACCESS_TOKEN` with the access token given to you from the authorisation section.

```shell
curl -X GET \
  BASE_URL/api/job \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN' \
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->get('BASE_URL/api/job', [
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
   "data":[
      {
         "id":142,
         "organisation_id":10,
         "reference":"1234567893",
         "number_applied":0,
         "job_title":"PHP Developer",
         "job_title_suggest":{
            "input":[
               "PHP Developer"
            ],
            "contexts":{
               "location":[
                  {
                     "lat":53.39396667480469,
                     "lon":-1.419806718826294
                  }
               ]
            }
         },
         "slug":"test/142/php-developer",
         "summary":"Lamp Developer",
         "description":"All of the skills",
         "benefits":null,
         "skills":null,
         "salary":{
            "from":0,
            "to":0,
            "text":"Competitive",
            "frequency":"ANNUALLY",
            "currency":{
               "iso_code":"GBP",
               "symbol":"£",
               "unicode":"£"
            }
         },
         "creator_name":"Test Martin",
         "location":{
            "display":"Sheffield, South Yorkshire",
            "postcode":{
               "id":22,
               "postcode":"S95AT"
            },
            "country":{
               "id":229,
               "iso":"GB",
               "name":"United Kingdom",
               "geo":{
                  "lon":0,
                  "lat":0
               }
            },
            "geo":{
               "lon":"-1.419806718826294",
               "lat":"53.39396667480469"
            }
         },
         "language":{
            "data":{
               "id":1,
               "iso_code":"en",
               "name":"English"
            }
         },
         "evergreen":false,
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
         "open_time_frame":{
            "gte":{
               "date":"2017-09-14 00:00:00.000000",
               "timezone_type":3,
               "timezone":"UTC"
            },
            "lte":{
               "date":"2017-10-14 00:00:00.000000",
               "timezone_type":3,
               "timezone":"UTC"
            }
         },
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
         "organisation":{
            "data":{
               "id":10,
               "handle":"test",
               "name":"Test"
            }
         },
         "category":{
            "data":{
               "id":6,
               "handle":"ANALYST",
               "parent":{
                  "id":749,
                  "handle":"SCIENTIFIC"
               }
            }
         },
         "type":{
            "data":{
               "id":1,
               "handle":"perm_fulltime"
            }
         },
         "media":{
            "data":[
               {
                  "id":8,
                  "type":"JOB_LOGO",
                  "path":"https://altenure-assets.s3-eu-west-1.amazonaws.com/images/pages/Ewmeyj2skemOh5DXTEOKpiP0zL2oNFzJUU370XJI.png"
               }
            ]
         },
         "address":{
            "id":16,
            "premise":"2 Rustic Court",
            "sub_premise":null,
            "thoroughfare":"",
            "locality":null,
            "postalcode":{
               "id":22,
               "postcode":"S95AT"
            },
            "geo":{
               "lat":53.39396667480469,
               "lon":-1.419806718826294
            },
            "country":{
               "id":229,
               "iso":"GB",
               "name":"United Kingdom",
               "geo":{
                  "lat":0,
                  "lon":0
               }
            }
         },
         "links":{
            "self":"BASE_URL/api/job/142",
            "apply":"BASE_URL/api/job/142/apply"
         }
      }
   ],
   "meta":{
      "pagination":{
         "total":3,
         "count":3,
         "per_page":25,
         "current_page":1,
         "total_pages":1
      },
      "aggregations":{
         "location.country.iso":[
            {
               "key":"gb",
               "doc_count":3
            }
         ],
         "category.parent.handle":[
            {
               "key":"scientific",
               "doc_count":2
            },
            {
               "key":"it_telecoms",
               "doc_count":1
            }
         ],
         "type.handle":[
            {
               "key":"perm_fulltime",
               "doc_count":3
            }
         ]
      }
   }
}
```

This endpoint retrieves all jobs.

### HTTP Request

`GET BASE_URL/api/job`

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
