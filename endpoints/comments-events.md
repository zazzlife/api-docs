Event Comments
=

Path: `/api/v1/comments/events`  

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting comments on an event|
|POST|used for posting a new comment on an event|

GET
-
####`/api/v1/comments/events/{eventId}?lastComment={commentId}`####
######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|eventId|integer||
|commentId|integer|`optional` used for pagination|

######Response: Collection of [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)######

POST
-
####`/api/v1/comments/events/{eventId}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
||string|the comment|

######Response: [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)######
