Photos
=

Path: `/api/v1/photos`  

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET||
|POST||
|PUT||
|DELETE||

GET
-
#####Getting user photos: `/api/v1/users/{userId}/photos?lastPhoto={photoId}`#####

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer||
|lastPhoto|integer|id of the last photo you received. (used for pagination)|

######Response: Collection of [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)######

----------------------

#####Getting a single photo: `/api/v1/photos/{photoId}`#####

######Response: [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)######

POST
-
####`/api/v1/photos`####

***Note: The only acceptable `Content Type` for this request is `multipart/form-data`***

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|photo|data|contents of the photo|
|description|string||
|albumId|int|`optional`|
|showInFeed|bool||
|categories|array of integers|category ids|

***showInFeed property should be `false` for the following scenarios:***
* photo is uploaded for an event in the create event page.
* photo is uploaded for a weekly in the create weekly page.


######Response: [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)######

PUT
-
####`/api/v1/photos/{photoId}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|description|string||
|albumId|int||

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to modify the photo|
|404|photo doesn't exist|


DELETE
-
####`/api/v1/photos/{photoId}`####

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to delete the photo|
