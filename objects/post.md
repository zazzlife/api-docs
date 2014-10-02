Post
=

|Name|Type|Description|
|----|----|-----------|
|postId|integer||
|message|string||
|time|DateTime|time of the event|
|fromUserId|integer|id of the user that creted the post|
|fromUserDisplayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|display photo of the user that created the post|
|fromUserDisplayName|string|display name of the user that created the post|
|toUserId|integer|will be provided if the user is posted on someone else's wall|
|toUserDisplayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|will be provided if the user is posted on someone else's wall|
|toUserDisplayName|string|will be provided if the user is posted on someone else's wall|
|categories|array of integer|category ids|
|TagUsers|string|"TagUsers" value should be all tagged users comma seperated ex. 5,6,7|
|Lockusers|string| "Lockusers" its value same as tag user that is comma seperated user id	ex. 5,6,7|
