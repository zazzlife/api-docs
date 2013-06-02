Albums
=

Path: `/api/v1/albums`  

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting user albums and a signle album|
|POST|used for creating a new album|
|PUT|used for editing an album|
|DELETE|used for deleting an album|

GET
-
###Getting user albums: `/api/v1/albums?userId={id}&lastAlbum={albumId}`###

*(right now this returns all user albums but we'll limit it to 5 or 10 albums, later on.)*

####Request parameters####
|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|user Id.|
|lastAlbum|integer|`optional` id of the last album that you've received. Used for pagination.|


####Response`(collection)`####

|Property Name|Type|Description|
|-------------|----|-----------|
|albumId|integer||
|userId|integer|id of the user that created the album.|
|name|string|album name|
|thumbnail|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||
|createdDate|DateTime||
|photos|CollectionOf [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)||
