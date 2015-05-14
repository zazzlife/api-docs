Posts
=

Path: `/api/v1/posts`  

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting a signle post|
|POST|used for creating a new post|
|PUT|used for editing a post|
|DELETE|used for deleting a post|

GET
-
#####Getting a post: `/api/v1/posts/{postId}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|postId|integer||

######Response: [Post](https://github.com/zazzlife/api-docs/blob/master/objects/post.md)######

POST
-
####`/api/v1/posts`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|message|string|message|
|toUserId|integer|`optional` should be provided if user is posting on someone else's wall|
|categories|array of integers|category ids|


######Response: [Post](https://github.com/zazzlife/api-docs/blob/master/objects/post.md)######

PUT
-
####`/api/v1/posts/{postId}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|message|string|message|
|toUserId|integer|`optional` should be provided if user is posting on someone else's wall|
|categories|array of integers|category ids|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to modify the post|
|404|post doesn't exist|


DELETE
-
####`/api/v1/posts/{postId}`####

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to delete the post|
