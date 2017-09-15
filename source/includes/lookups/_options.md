# Look Ups 

## Job Options

> Make sure to replace `ACCESS_TOKEN` with the access token given to you from the authorisation section.

```shell
curl -X GET \
  BASE_URL/admin/api/job/options \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN'
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->get('BASE_URL/admin/api/job/options', [
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
    "data": {
        "country": [
            {
                "id": 1,
                "iso": "AF",
                "name": "Afghanistan",
                "geo_lon": 0,
                "geo_lat": 0
            },
            {
                "id": 2,
                "iso": "AL",
                "name": "Albania",
                "geo_lon": 0,
                "geo_lat": 0
            }
        ],
        "job_type": [
            {
                "id": 1,
                "handle": "perm_fulltime",
                "name": "Perm Full-time"
            },
            {
                "id": 2,
                "handle": "perm_parttime",
                "name": "Perm Part-time"
            }
        ],
        "job_category": [
            {
                "id": 3,
                "handle": "ACCOUNTS_ADMIN",
                "name": "Accounts Admin"
            },
            {
                "id": 4,
                "handle": "ACCOUNTS_ASSISTANT",
                "name": "Accounts Assistant"
            }
        ],
        "salary_currency": [
            {
                "id": 1,
                "iso_code": "USD",
                "symbol": "$",
                "unicode": "&#36;"
            },
            {
                "id": 2,
                "iso_code": "EUR",
                "symbol": "€",
                "unicode": "&#128;"
            }
        ],
        "salary_frequency": [
            {
                "id": 1,
                "handle": "HOURLY",
                "name": "Hourly"
            },
            {
                "id": 7,
                "handle": "ANNUALLY",
                "name": "Annually"
            }
        ],
        "apply_type": [
            {
                "id": 1,
                "handle": "REDIRECT",
                "name": "Redirect applicants away to an external url"
            },
            {
                "id": 2,
                "handle": "SIGNUP",
                "name": "Applicants signup and are managed on the job board"
            }
        ]
    }
}
```

This endpoint retrieves all jobs option values that are required by the site.

### HTTP Request

`GET BASE_URL/admin/api/job/options`

### Headers

Parameter | Value | Description
--------- | ------- | -----------
Accept | application/vnd.jb.v1+json | The API version you want to access. 
Authorization | BEARER ACCESS_TOKEN | The access token from authorisation section