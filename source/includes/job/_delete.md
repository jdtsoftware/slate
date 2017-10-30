## Delete a Job

```shell
curl -X POST \
  BASE_URL/admin/api/job/{id}/delete \
  -H 'accept: application/vnd.jb.v1+json' \
  -H 'authorization: Bearer ACCESS_TOKEN'
```

```php
<?php

$http = new \GuzzleHttp\Client;

$response = $http->post('BASE_URL/admin/api/job/{id}/delete', [
    'headers' => [
        'accept' => 'application/vnd.jb.v1+json',
        'authorization' => 'Bearer ACCESS_TOKEN',
    ],
]);

return json_decode((string) $response->getBody(), true);
```

> The above command, on successful creation, returns JSON structured like this:

```json
{
    "data": {
        "acknowledged": true
    }
}
```

> Example Error 422 Response

```json
{
  "data": {
    "message": "422 Unprocessable Entity",
    "errors": {
      "job_id": [
        "Invalid job id."
      ]
    },
    "status_code": 422
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

This endpoint deletes a job.

### HTTP Request

`POST BASE_URL/admin/api/job/{id}/delete`