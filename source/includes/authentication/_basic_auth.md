## Basic Auth

We support basic auth access to the APIs. This is turned on an account by account basis depending on your need.
Please specify when requesting an access token that you would like Basic Auth Access.

When using basic auth you will need supply the following headers to all requests.

### Headers

Parameter | Value | Description
--------- | ------- | -----------
Client-Id | CLIENT_ID | Your api client id. 
Client-Secret | CLIENT_SECRET | Your api client secret. 
Authorization | BASIC Base64 USERNAME:PASSWORD | Your Basic Auth String.
