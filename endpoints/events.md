Events
=

Path: `/api/v1/events`  

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting user events or a signle event|
|POST|used for creating a new event|
|PUT|used for editing an event|
|DELETE|used for deleting an event|

GET
-
#####Getting user events: `/api/v1/users/{userId}/events?lastEvent={eventId}`#####

*Each call returns maximum 30 events in descending order*

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer|user Id.|
|lastEvent|integer|`optional` id of the last event that you've received. Used for pagination.|


######Response: collection of [Event](https://github.com/zazzlife/api-docs/blob/master/objects/event.md)######

-----------------------

#####Getting a single event: `/api/v1/events/{id}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|event Id.|

######Response: [Event](https://github.com/zazzlife/api-docs/blob/master/objects/event.md)######

POST
-
####`/api/v1/events`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|name|string|event name|
|city|string||
|description|string||
|isDateOnly|bool|set to `true` if user provided only a date|
|name|string|event name|
|latitude|float||
|longitude|float||
|location|string||
|photoId|int|photo id of the event|
|price|float||
|street|string||
|time|DateTime|Time of the event, it should be in [ISO 8601 format](http://en.wikipedia.org/wiki/ISO_8601) and in local time. Also it should specify the offset from UTC. Example: `2013-06-25T12:50:42.9868645+03:30`|

######Response: [Event](https://github.com/zazzlife/api-docs/blob/master/objects/event.md)######

PUT
-
####`/api/v1/events/{id}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|name|string|event name|
|city|string||
|description|string||
|isDateOnly|bool|set to `true` if user provided only a date|
|name|string|event name|
|latitude|float||
|longitude|float||
|location|string||
|photoId|int|photo id of the event|
|price|float||
|street|string||
|time|DateTime|Time of the event, it should be in [ISO 8601 format](http://en.wikipedia.org/wiki/ISO_8601) and in local time. Also it should specify the offset from UTC. Example: `2013-06-25T12:50:42.9868645+03:30`|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to modify the event|
|404|event doesn't exist|


DELETE
-
####`/api/v1/event/{id}`####

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to delete the event|
