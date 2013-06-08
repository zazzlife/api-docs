Login
=

Path: `/api/v1/login`  
***This request only requires you to pass the `AppId` and `Request Signature` in the `Authorization`Header***

Available methods:
<table>
    <tr><th>Method</th><th>Description</th></tr>
    <tr><td>POST</td><td>Used for logging in.</td></tr>
</table>

POST
-
###Request parameters###
<table>

    <tr><th>Property Name</th><th>Type</th><th>Description</th></tr>
    <tr><td>appId</td><td>integer</td><td>The application id that is provided to you.</td></tr>
    <tr><td>username</td><td>string</td><td></td></tr>
    <tr><td>password</td><td>string</td><td>It's exactly like signing the password for the Authorization header. It should be Base64 representation of the HMAC-SHA512 hash of the provided password.</td></tr>
</table>

###Response###

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|User Id.|
|accountType|enum|Possible values: (User, Club)|
|displayName|string|display name of the user. For clubs it'll be the club name and for users it's their full name or if it's empty their username.|
|displayPhoto|[object](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|the user profile photo.|

example:

    {
      "id":8,
      "accountType":"User",
      "displayName":"testUser",
      "displayPhoto":{
        "verySmallLink":"http://localhost:17433/Images/placeholder.gif",
        "smallLink":"http://localhost:17433/Images/placeholder.gif",
        "mediumLink":"http://localhost:17433/Images/placeholder.gif",
        "originalLink":"http://localhost:17433/Images/placeholder.gif"
      }
    }
