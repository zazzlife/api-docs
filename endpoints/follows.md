Follows
=

Path: `/api/v1/Follows`  

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting current user follows|
|POST|used for follow a user|
|DELETE|used for unfollow a user|

GET
-
#####Getting a list of users that the current user follows: `/api/v1/follows`#####

######Response: collection of [Follow](https://github.com/zazzlife/api-docs/blob/master/objects/follow.md)######

POST
-
#####Follow a user: `/api/v1/follows`#####

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
#####unfollow a user `/api/v1/follows/{userId}`#####


######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|id of the user to unfollow.|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid user id|
