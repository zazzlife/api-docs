Followers
=
Path: `/api/v1/followers/qrcode`

Available methods:

|Method|Description|
|------|-----------|
|POST|Add a new follower|

POST
-
#####Add new new follower: `/api/v1/followers/qrcode`#####

*this action makes another user to follow you*

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|id of the user to follow you|
|token|string|the token that you got from this [response](https://github.com/zazzlife/api-docs/blob/master/endpoints/qrcode.md)

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid user id or token|
|404|user not found|
