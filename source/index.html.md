---
title: Partneroid Public API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2
---

<h1>Partneroid Public API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Public API to be used by user

Base URLs:

- <a href="https://api.partneroid.com/v1">https://api.partneroid.com/v1</a>

# Authentication

- API Key (ApiKeyAuth)
  - Parameter Name: **x-metapair-token**, in: header.

<h1 id="partneroid-public-api-default">Default</h1>

## get\_\_competitors

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/competitors?url=string \
  -H 'Accept: application/json' \
  -H 'x-metapair-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/competitors?url=string HTTP/1.1
Host: api.partneroid.com
Accept: application/json

```

```javascript
var headers = {
  Accept: "application/json",
  "x-metapair-token": "API_KEY"
};

$.ajax({
  url: "https://api.partneroid.com/v1/competitors",
  method: "get",
  data: "?url=string",
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});
```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'x-metapair-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/competitors?url=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-metapair-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/competitors',
  params: {
  'url' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-metapair-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/competitors', params={
  'url': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/competitors?url=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-metapair-token": []string{"API_KEY"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/competitors", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /competitors`

Get competitors for a brand

<h3 id="get__competitors-parameters">Parameters</h3>

| Name | In    | Type   | Required | Description |
| ---- | ----- | ------ | -------- | ----------- |
| url  | query | string | true     | none        |

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "url": "http://example.com",
      "name": "string",
      "locations": ["string"],
      "image": {
        "inline": {
          "uri": "string"
        },
        "small": {
          "uri": "string"
        },
        "medium": {
          "uri": "string"
        },
        "large": {
          "uri": "string"
        }
      }
    }
  ]
}
```

<h3 id="get__competitors-responses">Responses</h3>

| Status | Meaning                                                          | Description | Schema |
| ------ | ---------------------------------------------------------------- | ----------- | ------ |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)          | none        | Inline |
| 400    | [Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1) | none        | Inline |

<h3 id="get__competitors-responseschema">Response Schema</h3>

Status Code **200**

| Name         | Type              | Required | Restrictions | Description |
| ------------ | ----------------- | -------- | ------------ | ----------- |
| » data       | [object]          | true     | none         | none        |
| »» url       | string(uri)\|null | false    | none         | none        |
| »» name      | string            | true     | none         | none        |
| »» locations | [string]          | true     | none         | none        |
| »» image     | object            | false    | none         | none        |
| »»» inline   | object            | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |
| »»» small    | object\|null      | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |
| »»» medium   | object\|null      | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |
| »»» large    | object\|null      | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |

Status Code **400**

| Name         | Type   | Required | Restrictions | Description |
| ------------ | ------ | -------- | ------------ | ----------- |
| » statusCode | number | true     | none         | none        |
| » error      | string | true     | none         | none        |
| » message    | string | true     | none         | none        |

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get\_\_brands

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/brands \
  -H 'Accept: application/json' \
  -H 'x-metapair-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/brands HTTP/1.1
Host: api.partneroid.com
Accept: application/json

```

```javascript
var headers = {
  Accept: "application/json",
  "x-metapair-token": "API_KEY"
};

$.ajax({
  url: "https://api.partneroid.com/v1/brands",
  method: "get",

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});
```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'x-metapair-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/brands',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-metapair-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/brands',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-metapair-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/brands', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/brands");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-metapair-token": []string{"API_KEY"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/brands", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /brands`

Filter brands by properties.

<h3 id="get__brands-parameters">Parameters</h3>

| Name       | In    | Type          | Required | Description |
| ---------- | ----- | ------------- | -------- | ----------- |
| locations  | query | array[string] | false    | none        |
| categories | query | array[string] | false    | none        |

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "url": "http://example.com",
      "name": "string",
      "locations": ["string"],
      "image": {
        "inline": {
          "uri": "string"
        },
        "small": {
          "uri": "string"
        },
        "medium": {
          "uri": "string"
        },
        "large": {
          "uri": "string"
        }
      }
    }
  ]
}
```

<h3 id="get__brands-responses">Responses</h3>

| Status | Meaning                                                          | Description | Schema |
| ------ | ---------------------------------------------------------------- | ----------- | ------ |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)          | none        | Inline |
| 400    | [Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1) | none        | Inline |

<h3 id="get__brands-responseschema">Response Schema</h3>

Status Code **200**

| Name         | Type              | Required | Restrictions | Description |
| ------------ | ----------------- | -------- | ------------ | ----------- |
| » data       | [object]          | false    | none         | none        |
| »» url       | string(uri)\|null | false    | none         | none        |
| »» name      | string            | true     | none         | none        |
| »» locations | [string]          | true     | none         | none        |
| »» image     | object            | false    | none         | none        |
| »»» inline   | object            | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |
| »»» small    | object\|null      | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |
| »»» medium   | object\|null      | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |
| »»» large    | object\|null      | false    | none         | none        |
| »»»» uri     | string            | false    | none         | none        |

Status Code **400**

| Name         | Type   | Required | Restrictions | Description |
| ------------ | ------ | -------- | ------------ | ----------- |
| » statusCode | number | true     | none         | none        |
| » error      | string | true     | none         | none        |
| » message    | string | true     | none         | none        |

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## get\__brands_{id}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.partneroid.com/v1/brands/{id} \
  -H 'x-metapair-token: API_KEY'

```

```http
GET https://api.partneroid.com/v1/brands/{id} HTTP/1.1
Host: api.partneroid.com

```

```javascript
var headers = {
  "x-metapair-token": "API_KEY"
};

$.ajax({
  url: "https://api.partneroid.com/v1/brands/{id}",
  method: "get",

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});
```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'x-metapair-token':'API_KEY'

};

fetch('https://api.partneroid.com/v1/brands/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'x-metapair-token' => 'API_KEY'
}

result = RestClient.get 'https://api.partneroid.com/v1/brands/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'x-metapair-token': 'API_KEY'
}

r = requests.get('https://api.partneroid.com/v1/brands/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.partneroid.com/v1/brands/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "x-metapair-token": []string{"API_KEY"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.partneroid.com/v1/brands/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /brands/{id}`

Get brand by brand id

<h3 id="get__brands_{id}-parameters">Parameters</h3>

| Name | In   | Type   | Required | Description |
| ---- | ---- | ------ | -------- | ----------- |
| id   | path | string | true     | none        |

<h3 id="get__brands_{id}-responses">Responses</h3>

| Status | Meaning                                                 | Description      | Schema |
| ------ | ------------------------------------------------------- | ---------------- | ------ |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Default Response | None   |

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>
