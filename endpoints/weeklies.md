Weeklies
=

Path: `/api/v1/weeklies`  

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting a signle weekly|
|POST|used for creating a new weekly|
|PUT|used for editing a weekly|
|DELETE|used for deleting a weekly|

GET
-
#####Getting a post: `/api/v1/weeklies/{weeklyId}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|weeklyId|integer||

######Response: [Weekly](https://github.com/zazzlife/api-docs/blob/master/objects/weekly.md)######

POST
-
####`/api/v1/weeklies`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|name|string||
|description|string||
|photoId|integer||
|dayOfTheWeek|enum|possible values are: `Sunday`, `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday`, `Saturday`|


######Response: [Weekly](https://github.com/zazzlife/api-docs/blob/master/objects/weekly.md)######

***Note: Only clubs can create weeklies and maximum limit is 7***

PUT
-
####`/api/v1/weeklies/{weeklyId}`####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|name|string||
|description|string||
|photoId|integer||
|dayOfTheWeek|enum|possible values are: `Sunday`, `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday`, `Saturday`|


######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to modify the weekly|
|404|weekly doesn't exist|


DELETE
-
####`/api/v1/weeklies/{weeklyId}`####

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to delete the weekly|
