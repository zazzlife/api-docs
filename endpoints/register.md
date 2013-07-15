Register
=

Path: `/api/v1/register`

Registering user
-

* HTTP Method should be `POST`
* Authorization header should be: `Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY`

###Request parameters###
|Property Name|Type|Description|
|-------------|----|-----------|
|username|string|`required`|
|email|string|`required`|
|password|string|`required` password in clear text (max 20 characters)|
|Gender|enum|`required` values can be one of (`Male`, `Female`, `NotSpecified`)|
|fullName|string|`optional`|
|accountType|enum|`required` for registering user it should be `User`|

example:

    POST /api/v1/register HTTP/1.1
    Host: localhost:17433
    Authorization: Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY
    Cache-Control: no-cache
    Content-Type: application/x-www-form-urlencoded
    
    username=Soroush&password=123&accountType=User&email=Soroush%40zazzlife.com&gender=Male&fullName=Soroush+Mirzaei

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
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzM4Nzk3MjQsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsInNjb3BlcyI6ImZ1bGwiLCJuYmYiOjEzNzM4NzYxMjR9.aJX5OrZe2mD09IX_7-KpTK0GbNGQAUFZ7wTTJaolW9A",
        "token_type": "Bearer",
        "expires_in": 3600,
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJpZnkiOiJQYkpycVpNRmswVDBHUXg0VlZ3VEZrczFuMXF2ZVhKcE4zL3N1WXZoVzl4c0JNZ2Zic2tBTWYyc3pTVG1OR2o5NmhlTXdGUnJvSzdqa0lndnFPZ3VFOEdiVmZZRTRyZFVwZGhzNG1TTTdJT3NZRTFyWERPVklPZUZCU1JwVnU3ek5zSXVDa2tjYVU0Y21vNkNybGZteFpDV3RNYy9FK0JJdkdneE9YOWxqOXc9IiwiaWQiOjEsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MSwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJyZWZyZXNoVG9rZW4iLCJzY29wZXMiOiJmdWxsIiwibmJmIjoxMzczODc2MTI0fQ.7tZqqD1bZe9rL2MJiOO3XH2WOy6YV1MroDP2d_VDcUA",
        "user": {
            "userId": 1,
            "accountType": "User",
            "isConfirmed": false,
            "displayName": "Soroush Mirzaei",
            "displayPhoto": {
                "verySmallLink": "http://localhost:17433/Images/placeholder.gif",
                "smallLink": "http://localhost:17433/Images/placeholder.gif",
                "mediumLink": "http://localhost:17433/Images/placeholder.gif",
                "originalLink": "http://localhost:17433/Images/placeholder.gif"
            }
        }
    }

###Error Response###
* `invalid_client`: the Authorization header is not set or is wrong.
* `invalid_request`: there was an error in the request, either one of the required properties are missing or they are not in a valid format. (you will receive a description which property was not in a valid format)


Registering club
-

* HTTP Method should be `POST`
* Authorization header should be: `Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY`

###Request parameters###
|Property Name|Type|Description|
|-------------|----|-----------|
|username|string|`required`|
|email|string|`required`|
|password|string|`required` password in clear text (max 20 characters)|
|clubName|string|`required`|
|clubAddress|string|`optional`|
|clubType|enum|`required` can be one of the following (`Bar`, `Lounge`, `Nightclub`, `ConcertVenue`, `StudentAssociation`, `Sorority`)|
|accountType|enum|`required` for registering club it should be `Club`|

example:

    POST /api/v1/register HTTP/1.1
    Host: localhost:17433
    Authorization: Basic hdi7o53NSeilrq7oQihy69PvH9BBQtw5QfcJy4ALBuY
    Cache-Control: no-cache
    Content-Type: application/x-www-form-urlencoded
    
    username=TestClub&password=123&accountType=Club&email=test%40test.com&clubName=my+awesome+club&clubAddress=the+address&clubType=Bar

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
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjEzNzM4ODA1NDAsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MiwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJhY2Nlc3NUb2tlbiIsInNjb3BlcyI6ImZ1bGwiLCJuYmYiOjEzNzM4NzY5NDB9.dOPSAha4XdMqXk0Mt51uD85RFaha8v9FgMgduhzD0mo",
        "token_type": "Bearer",
        "expires_in": 3600,
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ2ZXJpZnkiOiI3Y1hyV3cvNlFIZ1ZPYUpOYUVHK0IrU0RmR090NXp5cFhQaG9XR1VYaTdjSXFCTjJqMW90Yno4eWVRcTJHUHlVTmhJaVhFdHVBdFBqLzdCb2p3aFllZkR4dmdqaEloS0FYeUlPZHROVXd6RzBFYy9USEdxYVRXd1BRRjd4ZHB5djhKYTM3MGVlUndveHRXRXF3VWJDbTVPVXpyb0NPdWdvUTE2SnJOT3gybXc9IiwiaWQiOjIsImF1ZCI6IlphenogY2xpZW50cyIsInVzciI6MiwiY2xpZW50IjoxLCJpc3MiOiJodHRwczovL3d3dy56YXp6bGlmZS5jb20iLCJ0b2tlblR5cGUiOiJyZWZyZXNoVG9rZW4iLCJzY29wZXMiOiJmdWxsIiwibmJmIjoxMzczODc2OTQwfQ.eomYnKcalXzij01BLLiYmK1hZNfZ6anHatm5lx4Js6U",
        "user": {
            "userId": 2,
            "accountType": "Club",
            "isConfirmed": false,
            "displayName": "my awesome club",
            "displayPhoto": {
                "verySmallLink": "http://localhost:17433/Images/placeholder.gif",
                "smallLink": "http://localhost:17433/Images/placeholder.gif",
                "mediumLink": "http://localhost:17433/Images/placeholder.gif",
                "originalLink": "http://localhost:17433/Images/placeholder.gif"
            }
        }
    }
    
    
###Error Response###
* `invalid_client`: the Authorization header is not set or is wrong.
* `invalid_request`: there was an error in the request, either one of the required properties are missing or they are not in a valid format. (you will receive a description which property was not in a valid format)
