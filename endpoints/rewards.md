Rewards
=

Path: `/api/v1/rewards`  

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting user rewards|
|DELETE|used for deleting user rewards|

GET
-
#####Getting user rewards from current club: `/api/v1/rewards?userId={userId}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer||

######Response: Collection of [Reward](https://github.com/zazzlife/api-docs/blob/master/objects/reward.md)######

DELETE
-
####`/api/v1/rewards/{rewardId}`####

*this should be used when a user uses his reward*

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|current user is not authorized to delete the reward|
