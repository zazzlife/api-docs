User
=

User
-

|Name|Type|Description|
|----|----|-----------|
|id|integer||
|username|string||
|accountType|enum|can be one of the following: (User, Club)|
|profilePhotoId|integer|id of the profile photo (can be null).|
|profilePhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|url to the user profile photo|
|preferences|Preferences|user preferences|
|userDetails|UserDetails|only available when the `accountType` is `User`|
|clubDetails|ClubDetails|only available when the `accountType` is `Club`|

Preferences
-
|Name|Type|Description|
|----|----|-----------|
|syncFbEvents|bool|whether user wants to sync his facebook events with his zazz account.|
|syncFbPosts|bool|whether user wants to sync his facebook posts with his zazz account. (only available for clubs)|
|syncFbPhotos|bool|whether user wants to sync his facebook photos with his zazz account. (only available for clubs)|
|sendSyncErrorNotifications|bool|whether user wants to get notified by email when there is a facebook sync error|

ApiUserDetails
-
|Name|Type|Description|
|----|----|-----------|
|fullName|string||
|cityId|integer||
|city|[City](https://github.com/zazzlife/api-docs/blob/master/objects/city.md)||
|majorId|integer||
|major|[Major](https://github.com/zazzlife/api-docs/blob/master/objects/major.md)||
|schoolId|integer||
|school|[School](https://github.com/zazzlife/api-docs/blob/master/objects/school.md)||
|gender|enum|one of the following: (NotSpecified, Male, Female)|


ApiClubDetails
-
|Name|Type|Description|
|----|----|-----------|
|clubName|string||
|address|string||
|coverPhotoId|integer|can be null|
|coverPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|
|clubTypeId|integer||
|clubType|[ClubType](https://github.com/zazzlife/api-docs/blob/master/objects/clubtype.md)||
