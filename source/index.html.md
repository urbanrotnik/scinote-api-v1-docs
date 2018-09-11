---
title: SciNote V1 API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - teams
  - inventories
  - projects
  - experiments
  - tasks
  - errors

search: true
---

# Introduction

Welcome to the SciNote V1 API! You can use our API to access SciNote API endpoints.

This API documentation page was created with [Slate](https://github.com/lord/slate).

# Authentication

> To get an access token, use this code:

```shell
curl -d '{"grant_type": "password", "email": "<your_email>", "password": "<your_password>"}'
  -H "Content-Type: application/json" https://my-test.scinote.net/api/auth/token
```
> Make sure to replace `<your_email>` and `<your_password>` with your user's credentials.

> The above command returns JSON structured like this:

```json
{
    "token_type": "bearer",
    "access_token": "qwerty123456..."
}
```

SciNote uses JWT tokens to allow access to the API. You can get a new access token at https://my-test.scinote.net/api/auth/token.

SciNote expects for the API access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer qwerty123456...`

<aside class="notice">
You must replace <code>qwerty123456...</code> with your API access token.
</aside>

# Pagination

This API uses pagination as specified here [JSON API](http://jsonapi.org/format/#fetching-pagination)

Default page size is 10.

### Pagination Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Number of requested page.
page_size | 10 | Number of items returned per page.
