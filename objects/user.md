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
|preferences|[Preferences](https://github.com/zazzlife/api-docs/blob/master/objects/user.md#preferences)|user preferences|
|userDetails|[UserDetails](https://github.com/zazzlife/api-docs/blob/master/objects/user.md#userdetails)|only available when the `accountType` is `User`|
|clubDetails|[ClubDetails](https://github.com/zazzlife/api-docs/blob/master/objects/user.md#clubdetails)|only available when the `accountType` is `Club`|

Preferences
-
|Name|Type|Description|
|----|----|-----------|
|syncFbEvents|bool|whether user wants to sync his facebook events with his zazz account.|
|syncFbPosts|bool|whether user wants to sync his facebook posts with his zazz account. (only available for clubs)|
|syncFbPhotos|bool|whether user wants to sync his facebook photos with his zazz account. (only available for clubs)|
|sendSyncErrorNotifications|bool|whether user wants to get notified by email when there is a facebook sync error|

UserDetails
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


ClubDetails
-
|Name|Type|Description|
|----|----|-----------|
|clubName|string||
|address|string||
|coverPhotoId|integer|can be null|
|coverPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)|
|clubTypeId|integer||
|clubType|enum|one of the following: (Bar, Lounge, Nightclub, ConcertVenue, StudentAssociation, Sorority|
