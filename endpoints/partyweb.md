Partyweb
=
***Name and the return object of this endpoint is subject to change***

Path: `/api/v1/partyweb`  

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting current user's party web|
|POST|used for follow a user|
|DELETE|used for unfollow a user|

GET
-
#####Getting a list of users that are in the current user party web: `/api/v1/partyweb`#####

######Response: collection of [PartyWebFollow](https://github.com/zazzlife/api-docs/blob/master/objects/partywebfollower.md)######

POST
-
#####Add a new user to current user's party web (aka following another user): `/api/v1/partyweb`#####

*note that if the target user account type is `User` this action will send a follow request.*

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
||integer|id of the user to follow.|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid user id|
|404|user doesn't exist|


DELETE
-
#####unfollow a user `/api/v1/partyweb/{userId}`#####


######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|id of the user to unfollow.|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid user id|
