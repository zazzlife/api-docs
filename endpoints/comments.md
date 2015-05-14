Comments
=

Path: `/api/v1/comments`

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|PUT|used for editing a comment|
|DELETE|used for deleting a comment|

PUT
-
####`/api/v1/comments/{commentId}`####
######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|commentText|string||

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id or comment text|
|403|user is not authorized to modify the comment|
|404|comment doesn't exist|

DELETE
-
####`/api/v1/comments/{commentId}`####

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to remove the comment|
