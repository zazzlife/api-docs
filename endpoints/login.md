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
<table>
    <tr><th>Property Name</th><th>Type</th><th>Description</th></tr>
    <tr><td>id</td><td>integer</td><td>User Id.</td></tr>
    <tr><td>accountType</td><td>enum</td><td>Possible values: User | Club</td></tr>
    <tr><td>displayName</td><td>string</td><td>display name of the user. For clubs it'll be the club name and for users it's their full name or if it's empty their username.</td></tr>
    <tr><td>displayPhoto</td><td>object</td><td>the user profile photo.</td></tr>
</table>
