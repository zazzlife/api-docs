Feed
=

|Name|Type|Description|
|----|----|-----------|
|userId|integer|id of the user that created the feed|
|userDisplayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|display photo of the user that created the feed|
|userDisplayName|string|display name of the user that created the feed|
|canCurrentUserRemoveFeed|bool|it is true when the current user is not the feed owner but can remove the feed, for example when someone else has posted on their wall, they can remove that post.|
|feedType|enum|can be one of the following (post, event, photo)|
|time|DateTime||
|photos|collection of [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)|this is only available when the feed type is `photo`|
|post|[Post](https://github.com/zazzlife/api-docs/blob/master/objects/post.md)|this is only available when the feed type is `post`|
|event|[Event](https://github.com/zazzlife/api-docs/blob/master/objects/event.md)|this is only available when the feed type is `event`|
|comments|collection of [Comment](https://github.com/zazzlife/api-docs/blob/master/objects/comment.md)||

* If the feed type is `Photo` and its `photos` property has more than one photo in it, the `comments` property will be null.
