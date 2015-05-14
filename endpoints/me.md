Login
=

Path: `/api/v1/me`  

* Authorization header should be: `AuthToken <access_token>`

This url gives some basic information about the current user, it requires a valid access token.

###Request###

example:

    GET /api/v1/me HTTP/1.1
    Host: localhost:17433
    Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzQyMTMxNzAsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsInNjb3BlcyI6ImZ1bGwiLCJuYmYiOjEzNzQyMDk1NzB9.WOadw0ZhtYWC2EgGOCo9wjRBvTe4Cu9C1THia8u4nIk
    Cache-Control: no-cache

###Response###

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|User Id.|
|accountType|enum|Possible values: (User, Club)|
|isConfirmed|bool|`true` if user has confirmed his email address|
|displayName|string||
|displayPhoto|[object](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||

example:

    {
        "userId": 1,
        "accountType": "User",
        "isConfirmed": true,
        "displayName": "Soroush Mirzaei",
        "displayPhoto": {
            "verySmallLink": "http://localhost:17433/Images/placeholder.gif",
            "smallLink": "http://localhost:17433/Images/placeholder.gif",
            "mediumLink": "http://localhost:17433/Images/placeholder.gif",
            "originalLink": "http://localhost:17433/Images/placeholder.gif"
        }
    }
