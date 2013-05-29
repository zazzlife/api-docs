Event
=

|Name|Type|Description|
|----|----|-----------|
|eventId|integer||
|name|string|event name|
|description|string|event description|
|time|DateTime|time of the event|
|utcTime|DateTime|time of the event in UTC|
|location|string|location of the event|
|street|string||
|city|string||
|price|float||
|latitude|float||
|longitude|float||
|createdTime|DateTime|time the event was created|
|isFacebookEvent|bool||
|facebookLink|string||
|isDateOnly|bool||
|userId|integer|id of the user that creted the event|
|userDisplayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|display photo of the user that created the event|
|userDisplayName|string|display name of the user that created the event|
|imageUrl|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|picture of the event.|
|photoId||this is used when an event with picture is created by you.|


* Since this is synced with facebook the following properties might be null: (description, location, street, city, price, latitude, longitude, facebookLink)
* `photoId` will be null when you're getting the event from server, but it should be provided by you when a user creates an event with picture.
