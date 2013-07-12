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
|access_token|string|use this access token in auth header for all resource API calls|
|token_type|string|scheme of the token|
|expires_in|integer|token expiration time in seconds|
|refresh_token|string|use this token to get a new access token|
|user.userId|integer|User Id.|
|user.accountType|enum|Possible values: (User, Club)|
|user.isConfirmed|bool|`true` if user has confirmed his email address|
|user.displayName|string|display name of the user. For clubs it'll be the club name and for users it's their full name or if it's empty their username.|
|user.displayPhoto|[object](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|the user profile photo.|

example:

    {
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzM2MTQ0MDksImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsIm5iZiI6MTM3MzYxMDgwOX0.-hHF7Cp7EOT-Rh92ipPmBOdDgZ2fYB-kaaAT6sHFW38",
        "token_type": "Bearer",
        "expires_in": 3600,
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJpZnkiOiJaZ0lkVzZPajRiWVd2K2ZLdWxidnVVajA4UC9qcHNOSzZ6eU9zZFpRQzJORzFHVWVsOFpJWEx2TDhmRGVkTVEyWkdkblZnejUrYUFmZ0pIRkJJbytsWGVaaFQzMVFQQ0EraFFpdUI2SzVzV0xGMFZiRGdTUlg4aFJxYUcxM28vVzRmTldyaWtOM3p6SDB3ZlM5Z29hcWljbktUa1hMZnV2SHRlZ1BDdk0xNGM9IiwiaWQiOjEsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJyZWZyZXNoVG9rZW4iLCJuYmYiOjEzNzM2MTA4MDh9.UIfWpBg0YPQGL3q28OQTO_BINViI4LRgO0AxjpxPdhY",
        "user": {
            "userId": 1,
            "accountType": "User",
            "isConfirmed": false,
            "displayName": "Soroush",
            "displayPhoto": {
                "verySmallLink": "http://localhost:17433/Images/placeholder.gif",
                "smallLink": "http://localhost:17433/Images/placeholder.gif",
                "mediumLink": "http://localhost:17433/Images/placeholder.gif",
                "originalLink": "http://localhost:17433/Images/placeholder.gif"
            }
        }
    }
