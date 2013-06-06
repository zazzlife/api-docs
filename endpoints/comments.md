Comments
=

Path: `/api/v1/comments`  

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
