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
#####Getting user albums: `/api/v1/albums?userId={id}&lastAlbum={albumId}`#####

*(right now this returns all user albums but we'll limit it to 5 or 10 albums, later on.)*

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|user Id.|
|lastAlbum|integer|`optional` id of the last album that you've received. Used for pagination.|


######Response: collection of [Album](https://github.com/zazzlife/api-docs/blob/master/objects/album.md)######

-----------------------

#####Getting a single album: `/api/v1/albums/{id}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|album Id.|

######Response: [Album](https://github.com/zazzlife/api-docs/blob/master/objects/album.md)######

POST
-
####`/api/v1/albums`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|name|string|album name|


######Response: [Album](https://github.com/zazzlife/api-docs/blob/master/objects/album.md)######

PUT
-
####`/api/v1/albums/{id}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|name|string|album name|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to modify the album|


