---
title: SciNote V1 API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - teams
  - inventories
  - inventory_columns
  - inventory_column_list_items
  - inventory_items
  - inventory_cells
  - results
  - errors

search: true
---

# Introduction

Welcome to the SciNote V1 API! You can use our API to access SciNote API endpoints.

This API documentation page was created with [Slate](https://github.com/lord/slate).

# Authentication

SciNote uses JWT tokens to allow access to the API and OAuth 2 protocol for token generation using authorization code flow.

First, it is needed to get authorization code at this endpoint: GET /oauth/authorize, please see example of such request.

> To get an authorization code, use this code:

```shell
curl https://server-name/oauth/authorize?client_id=<client_id>&<redirect_uri>&response_type=code
```
> Where `<client_id>` is your application registration id, `<redirect_uri>` your application redirect URI.

> The above command redirects back to your application with authorization code

Now you can get a new access token at /oauth/token with POST request. Once it expires, use refresh token to get new access token.

Post here with authorization code for `authorization_code` grant type or `refresh_token` for refresh token type. This corresponds to the token endpoint, section 3.2 of the OAuth 2 RFC

> To get an access token, use this code:

```shell
curl -F grant_type=authorization_code \
-F client_id=<client_app_id> \
-F client_secret=<client_app_secret> \
-F code=<authorization_code> \
-F redirect_uri=<client_app_redirect_url> \
-X POST https://server-name/oauth/token
```

> The above command returns JSON structured like this:

```json
{
    "access_token":"qwerty123456...",
    "token_type":"bearer",
    "expires_in":7200,
    "refresh_token":"qwerty123456..."}
}
```

> And for renewal, use this code:

```shell
curl -F grant_type=refresh_token \
-F client_id=<client_app_id> \
-F client_secret=<client_app_secret> \
-F refresh_token=<refresh_token> \
-F redirect_uri=<client_app_redirect_url> \
-X POST https://server-name/oauth/token
```

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
