Photo
=

|Name|Type|Description|
|----|----|-----------|
|photoId|integer||
|albumId|integer|will be null if the photo isn't in an album|
|description|string||
|photoLinks|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||
|userId|integer|id of the uploader|
|userDisplayName|string|display name of the uploader|
|userDisplayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|display photo of the uploader|
|categories|array of integer|category ids|
|TagUser|string|"TagUser" value should be all tagged users comma seperated ex. 5,6,7|
