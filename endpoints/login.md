Login
=

Path: `/api/v1/token`  

Getting an access token
-
* HTTP Method should be `POST`
* Authorization header should be: `Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY`
* Content-Type should be: `application/x-www-form-urlencoded`

###Request parameters###
|Property Name|Type|Description|
|-------------|----|-----------|
|grant_type|string|grant type should be set to `password`|
|username|string|username in clear text|
|password|string|password in clear text|
|scope|string|scope should be set to `full`|

example:

    POST /api/v1/token HTTP/1.1
    Host: localhost:17433
    Authorization: Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY
    Cache-Control: no-cache
    Content-Type: application/x-www-form-urlencoded
    
    grant_type=password&username=soroush&password=123&scope=full

###Success Response###

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|the user id for Zazz|
|access_token|string|use this access token in auth header for all resource API calls|
|token_type|string|scheme of the token|
|expires_in|integer|token expiration time in seconds|
|refresh_token|string|use this token to get a new access token|

example:

    {
        "userId": 3,
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzM2MTQ0MDksImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsIm5iZiI6MTM3MzYxMDgwOX0.-hHF7Cp7EOT-Rh92ipPmBOdDgZ2fYB-kaaAT6sHFW38",
        "token_type": "Bearer",
        "expires_in": 3600,
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJpZnkiOiJaZ0lkVzZPajRiWVd2K2ZLdWxidnVVajA4UC9qcHNOSzZ6eU9zZFpRQzJORzFHVWVsOFpJWEx2TDhmRGVkTVEyWkdkblZnejUrYUFmZ0pIRkJJbytsWGVaaFQzMVFQQ0EraFFpdUI2SzVzV0xGMFZiRGdTUlg4aFJxYUcxM28vVzRmTldyaWtOM3p6SDB3ZlM5Z29hcWljbktUa1hMZnV2SHRlZ1BDdk0xNGM9IiwiaWQiOjEsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJyZWZyZXNoVG9rZW4iLCJuYmYiOjEzNzM2MTA4MDh9.UIfWpBg0YPQGL3q28OQTO_BINViI4LRgO0AxjpxPdhY"
    }

###Error Response###
* `unsupported_grant_type`: `grant_type` is not set to `password`
* `invalid_client`: the Authorization header is not set or is wrong.
* `invalid_request`: one of the following is missing: `scope`, `username`, `password`
* `invalid_scope`: the scope is invalid, it should be `full`
* `invalid_grant`: the `username` or `password` is wrong

example:

    {"error":"invalid_grant"}

From now on, you should send the `access token` that you received with all requests, to access resources.

example:

    GET /api/v1/users/1/profile HTTP/1.1
    Host: localhost:17433
    Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzM2MTQ0MDksImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsIm5iZiI6MTM3MzYxMDgwOX0.-hHF7Cp7EOT-Rh92ipPmBOdDgZ2fYB-kaaAT6sHFW38
    Cache-Control: no-cache
    Content-Type: application/x-www-form-urlencode


Refreshing access token
-
* HTTP Method should be `POST`
* Authorization header should be: `Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY`
* Content-Type should be: `application/x-www-form-urlencoded`

###Request parameters###
|Property Name|Type|Description|
|-------------|----|-----------|
|grant_type|string|grant type should be set to `refresh_token`|
|refresh_token|string|the refresh token that you got from logging in|


example:

    POST /api/v1/token HTTP/1.1
    Host: localhost:17433
    Authorization: Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY
    Cache-Control: no-cache
    Content-Type: application/x-www-form-urlencoded
    
    grant_type=refresh_token&refresh_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJpZnkiOiJaZ0lkVzZPajRiWVd2K2ZLdWxidnVVajA4UC9qcHNOSzZ6eU9zZFpRQzJORzFHVWVsOFpJWEx2TDhmRGVkTVEyWkdkblZnejUrYUFmZ0pIRkJJbytsWGVaaFQzMVFQQ0EraFFpdUI2SzVzV0xGMFZiRGdTUlg4aFJxYUcxM28vVzRmTldyaWtOM3p6SDB3ZlM5Z29hcWljbktUa1hMZnV2SHRlZ1BDdk0xNGM9IiwiaWQiOjEsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJyZWZyZXNoVG9rZW4iLCJuYmYiOjEzNzM2MTA4MDh9.UIfWpBg0YPQGL3q28OQTO_BINViI4LRgO0AxjpxPdhY


###Success Response###

|Property Name|Type|Description|
|-------------|----|-----------|
|access_token|string||
|token_type|string||
|expires_in|integer||

example:

    {
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzM2MTU1MzksImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsIm5iZiI6MTM3MzYxMTkzOX0.yXm7IcoMFgC_BfT5vqPDocmgpss5LD_uCcIwmBMPqn8",
        "token_type": "Bearer",
        "expires_in": 3600
    }
    
###Error Response###
* `unsupported_grant_type`: `grant_type` is not set to `refresh_token`
* `invalid_client`: the Authorization header is not set or is wrong.
* `invalid_request`: `refresh_token` is missing
* `invalid_scope`: the scope is invalid, it should be `full`
* `invalid_grant`: the `refresh token` has been revoked. you need to show the login screen and obtain new tokens.

example:

    {"error":"invalid_grant"}

You can get basic info about the current user using this [endpoint](https://github.com/zazzlife/api-docs/blob/master/endpoints/me.md)
