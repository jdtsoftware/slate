# Authentication

The Job Space supports multiple authentication methods. These are all based upon Oauth2. When requesting access to the api please specify which
type you would like to be set up for. We have the right to change which type you are setup on depending on your use case.

The Job Space uses API keys to allow access to the API. You can request new API key by emailing us api@thejobspace.com.

The Job Space expects all API requests to the server to include a authorisation bearer token to be in a header that looks like the following:

`Authorization: Bearer OAUTH_ACCESS_TOKEN`

<aside class="notice">
You must replace <code>OAUTH_ACCESS_TOKEN</code> with your access token generated from /oauth/token using your API key.
</aside>
