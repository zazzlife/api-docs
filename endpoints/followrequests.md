FollowRequests
=

Path: `/api/v1/followrequests`  

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting follow requests|
|DELETE|used for accepting or rejecting a follow request|

GET
-
#####Getting follow requests: `/api/v1/followrequests`#####

######Response: collection of [FollowRequest](https://github.com/zazzlife/api-docs/blob/master/objects/followrequest.md)######

DELETE
-
####`/api/v1/followrequests/{userId}?action={accept/reject}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|id of the user that sent the request|
|action|string|can be either `accept` or `reject`|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid `userId` or `action`|
|403|user is not authorized to do this|
