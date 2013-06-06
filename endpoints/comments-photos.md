Photo Comments
=

Path: `/api/v1/comments/photos`  

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting comments on a photo|
|POST|used for posting a new comment on a photo|

GET
-
####`/api/v1/comments/photos/{photoId}?lastComment={commentId}`####
######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|photoId|integer||
|commentId|integer|`optional` used for pagination|

######Response: Collection of [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)######

POST
-
####`/api/v1/comments/photos/{photoId}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
||string|the comment|

######Response: [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)######
