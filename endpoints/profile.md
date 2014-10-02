User Profile
=

Path: `/api/v1/users/{id}/profile`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting user profile|

GET
-
#####Getting user profile: `/api/v1/users/{id}/profile?lastFeed={lastFeed}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|the user id|
|lastFeed|integer|`optional` id of the last feed that you've received. (used for pagination)|

######Response:######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|user id|
|accountType|enum|can be one of the following: (User, Club)|
|displayName|string||
|displayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||
|followRequestAlreadySent|bool|`true` if the current user has already sent a follow request.|
|followersCount|integer||
|isSelf|bool|`true` if it's profile of the current user|
|isCurrentUserFollowingTargetUser|bool|`true` if current user follows the user|
|isTargetUserFollowingCurrentUser|bool|`true` if user follows the current user|
|feeds|collection of [Feed](https://github.com/zazzlife/api-docs/blob/master/objects/feed.md)|activity feed of the user|
|photos|collection of [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)|latest uploaded photos (currently it returns maximum 15 photos)|
|userDetails|[UserDetails](https://github.com/zazzlife/api-docs/blob/master/objects/user.md#userdetails)|only available when the `accountType` is `User`|
|clubDetails|[ClubDetails](https://github.com/zazzlife/api-docs/blob/master/objects/user.md#clubdetails)|only available when the `accountType` is `Club`|
|weeklies|collection of [Weekly](https://github.com/zazzlife/api-docs/blob/master/objects/weekly.md)|only available when the `accountType` is `Club`|

GETTING ALL USER
-
#####Getting all user: `/api/v1/users/getallusers`#####

######Request parameters######

No Request

######Response:######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|user id|
|accountType|enum|can be one of the following: (User, Club)|
|displayName|string||
|displayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||
|followRequestAlreadySent|bool|`true` if the current user has already sent a follow request.|
|followersCount|integer||
|isSelf|bool|`true` if it's profile of the current user|
|isCurrentUserFollowingTargetUser|bool|`true` if current user follows the user|
|isTargetUserFollowingCurrentUser|bool|`true` if user follows the current user|
|feeds|collection of [Feed](https://github.com/zazzlife/api-docs/blob/master/objects/feed.md)|activity feed of the user|
|photos|collection of [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)|latest uploaded photos (currently it returns maximum 15 photos)|


GETTING ALL USER
-
#####Getting all user: `/api/v1/users/getallclubs`#####

######Request parameters######

No Request

######Response:######

|Property Name|Type|Description|
|-------------|----|-----------|
|id|integer|user id|
|accountType|enum|can be one of the following: (User, Club)|
|displayName|string||
|displayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||
|followRequestAlreadySent|bool|`true` if the current user has already sent a follow request.|
|followersCount|integer||
|isSelf|bool|`true` if it's profile of the current user|
|isCurrentUserFollowingTargetUser|bool|`true` if current user follows the user|
|isTargetUserFollowingCurrentUser|bool|`true` if user follows the current user|
|feeds|collection of [Feed](https://github.com/zazzlife/api-docs/blob/master/objects/feed.md)|activity feed of the user|
|photos|collection of [Photo](https://github.com/zazzlife/api-docs/blob/master/objects/photo.md)|latest uploaded photos (currently it returns maximum 15 photos)|
