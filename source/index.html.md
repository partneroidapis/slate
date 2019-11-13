---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript
  - shell
  - ruby
  - python

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Partneroid Competitors API! You can use our API to access competitor API endpoints, which can get information on competitors data from our database.

We have language bindings in JavaScript! You can view code examples in the dark area to the right.

# Authentication

> To authorize, use this code:

```ruby

```

```python

```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
```

> Make sure to replace `YOUR_API_KEY` with your API key.

Competitor API uses API keys to allow access to the API. You can register a new Competitor API key at our [developer portal](https://developers.partneroid.com).

Competitor API expects for the API key to be included in all API requests to the server in a header that looks like the following:

```headers
{
  x-metapair-token: YOUR_API_KEY
}
```

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

# Competitors

## Get Competitors

```ruby

```

```python

```

```shell
curl https://development.api.partneroid.com/v1/competitors?url=YOUR_SEARCH_URL -h x-metapair-token=YOUR_API_KEY
```

```javascript
fetch(
  `https://development.api.partneroid.com/v1/competitors?url=YOUR_SEARCH_URL`,
  {
    method: "GET",
    headers: {
      "x-metapair-token": "YOUR_API_KEY"
    }
  }
);
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "IBM",
    "locations": [],
    "image": {
      "inline": {
        "uri": "data:image/png;base64,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"
      },
      "small": null,
      "medium": null,
      "large": null
    }
  }
]
```

This endpoint retrieves competitors.

### HTTP Request

`GET https://development.api.partneroid.com/v1/competitors?url=<YOUR_SEARCH_URL>`

### URL Parameters

| Parameter | Description                                      |
| --------- | ------------------------------------------------ |
| url       | The company url you want to get competitors for. |
