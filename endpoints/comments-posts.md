Post Comments
=

Path: `/api/v1/comments/posts`  

Available methods:

* Authorization header should be: `AuthToken <access_token>`

|Method|Description|
|------|-----------|
|GET|used for getting comments on a post|
|POST|used for posting a new comment on a post|

GET
-
####`/api/v1/comments/posts/{postId}?lastComment={commentId}`####
######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|postId|integer||
|commentId|integer|`optional` used for pagination|

######Response: Collection of [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)######

POST
-
####`/api/v1/comments/posts/{postId}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
||string|the comment|

######Response: [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)######
