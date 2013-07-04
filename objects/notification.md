Notification
=

|Name|Type|Description|
|----|----|-----------|
|userId|integer||
|displayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||
|displayName|string||
|notificationType|enum|can be one of the following (`FollowRequestAccepted`, `CommentOnPhoto`, `CommentOnPost`, `CommentOnEvent`, `NewEvent`, `WallPost`)|
|isRead|bool|`true` if user has already seen this notification|
|time|DateTime||
|photo|[Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)|this is only available when the `notificationType` is `CommentOnPhoto`|
|post|[Post](https://github.com/zazzlife/api-docs/blob/master/objects/post.md)|this is only available when the `notificationType` is `CommentOnPost` or `WallPost`|
|event|[Event](https://github.com/zazzlife/api-docs/blob/master/objects/event.md)|this is only available when the `notificationType` is `CommentOnEvent` or `NewEvent`|
