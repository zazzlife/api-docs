Comment
=

|Name|Type|Description|
|----|----|-----------|
|commentId|integer||
|userId|integer|id of the user that wrote the comment|
|userDisplayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|display photo of the user that wrote the comment|
|userDisplayName|string|display name of the user that wrote the comment|
|commentText|string|the comment!|
|isFromCurrentUser|bool|is true of the user that is browsing left the comment, this is useful when you might want to show edit/remove for that comment.|
|time|DateTime|time of the comment|
