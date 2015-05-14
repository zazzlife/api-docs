EventInvitation
=

Path: `/api/v1/eventinvitation` 

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|POST|used for inviting users|

POST
-
####`/api/v1/events`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|eventId|int|event id|
|toUserId|int[]|array of user id to whom send the event invitation|
