Categories Feed
=

Path: `/api/v1/categories/{id}/feed` 

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET||

GET
-
####`/api/v1/categories/{id}/feed?lastFeed={lastFeed}`####
######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|string|you can send a comma seperated ids example: `1,2,3`|
|lastFeed|integer|`optional` id of the last feed that you've received. (used for pagination)|

######Response: collection of [Feed](https://github.com/zazzlife/api-docs/blob/master/objects/feed.md)######
