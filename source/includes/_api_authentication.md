## Authentication

### Retrieve an access token

> To retrieve a bearer token, use this code:

```shell
curl --request POST \
  --url https://www.nousrassemble.com/fr/oauth/access_token \
  --header 'content-type: multipart/form-data; boundary=---011000010111000001101001' \
  --form grant_type=password \
  --form client_id=120e3fc4c59a394f8560c8b8b8759b \
  --form client_secret=a204abcd1d983434f92b10f2ea62ff \
  --form username=THE_USER_NAME \
  --form password=THE_USER_PASSWORD \
```

```php
<?php

$client = new http\Client;
$request = new http\Client\Request;

$body = new http\Message\Body;
$body->addForm([
  'grant_type'    => 'password',
  'client_id'     => '120e3fc4c59a394f8560c8b8b8759b',
  'client_secret' => 'a204abcd1d983434f92b10f2ea62ff',
  'username'      => 'THE_USER_NAME',
  'password'      => 'THE_USER_PASSWORD',
], null);

$request->setRequestUrl('https://www.nousrassemble.com/fr/oauth/access_token');
$request->setRequestMethod('POST');
$request->setBody($body);

$client->enqueue($request)->send();
$response = $client->getResponse();

echo $response->getBody();
```

> You should retrieve this kind of object:

```json
{
  "access_token": "mn4KabcC2P8CLw5LU5xIb8Zsx16aALXRXnHhA01b",
  "token_type": "Bearer",
  "expires_in": 31536000,
  "refresh_token": "bcuA27CuNtHOzyMakYbXlsqp1JRQ92vE17oAggyb"
}
```

**nousrassemble** API needs authenticated users to execute endpoints. **nousrassemble** uses classic OAuth2 system to authenticate users.

You need a `client_id` and `client_secret` to retrieve an access token.

<aside class="notice">
You must replace <code>client_id</code> and <code>client_secret</code> with your personal credentials.
<p><code>username</code> and <code>password</code> are user credentials. If you use an app without need to authenticate user, you can create a <em>static</em> user especially for this.</p>
</aside>

Once you get the `access_token`, you will be able to keep it in your application for 31536000 seconds (1 year).

### Use an access token

Now you have an access token, you can reach endpoints just be setting Authorization header to `Bearer access_token`.

> To retrieve proposal list for a tenant:

```shell
curl \
	-X GET
	-H "Authorization: Bearer mn4KabcC2P8CLw5LU5xIb8Zsx16aALXRXnHhA01b"
	-H "Cache-Control: no-cache"
	'https://grenoble.nousrassemble.com/fr/api/proposals?include=createdby,themes'
```

```php
<?php

$client = new http\Client;
$request = new http\Client\Request;

$request->setRequestUrl('https://grenoble.nousrassemble.com/fr/api/proposals');
$request->setRequestMethod('GET');
$request->setQuery(new http\QueryString([
  'include' => 'createdby,themes'
]));

$request->setHeaders(array(
  'authorization' => 'Bearer mn4KabcC2P8CLw5LU5xIb8Zsx16aALXRXnHhA01b'
));

$client->enqueue($request)->send();
$response = $client->getResponse();

echo $response->getBody();
```