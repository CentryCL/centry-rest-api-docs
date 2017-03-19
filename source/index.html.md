---
title: API Reference

language_tabs:
  - shell: cURL
  - ruby: Ruby
  - php: PHP

toc_footers:
  - <a href='https://www.centry.cl'>Log in to get an API Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - products
  - orders
  - webhooks
  - errors

search: true
---

# Introduction

Welcome to Centry API. You can use our API to access Centry API endpoints, which can get information on various resources in our database.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'Centry'

api = Centry::APIClient.authorize!('your_centry_api_key')
```

```python
import Centry

api = Centry.authorize('your_centry_api_key')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: your_centry_api_key"
```

```javascript
const Centry = require('Centry');

let api = Centry.authorize('your_centry_api_key');
```

> Make sure to replace `your_centry_api_key` with your API key.

Centry uses API keys to allow access to the API. You can register a new Centry API key at our [developer portal](http://example.com/developers).

Centry expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: your_centry_api_key`

<aside class="notice">
You must replace <code>your_centry_api_key</code> with your personal API key.
</aside>

