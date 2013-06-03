Feeds
=

Path: `/api/v1/feeds`  

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting feeds|

GET
-
#####Getting all feeds for the current user: `/api/v1/feeds?lastFeed={lastFeed}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|lastFeed|integer|`optional` id of the last feed that you've received. (used for pagination)|

######Response: collection of [Feed](https://github.com/zazzlife/api-docs/blob/master/objects/feed.md)######

-----------------------

#####Getting activity feed of a user: `/api/v1/feeds/{userId}?lastFeed={lastFeed}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|user id|
|lastFeed|integer|`optional` id of the last feed that you've received. (used for pagination)|

######Response: collection of [Feed](https://github.com/zazzlife/api-docs/blob/master/objects/feed.md)######
