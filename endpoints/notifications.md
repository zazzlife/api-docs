Notifications
=

Path: `/api/v1/notifications` 

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting notifications|
|DELETE|used for deleting a notification|

GET
-
#####Getting notifications: `/api/v1/notifications?lastNotification={notificationId}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|lastNotification|integer (64 bit)|`optional` used for pagination|

######Response: Collection of [Notification](https://github.com/zazzlife/api-docs/blob/master/objects/notification.md)######

* this will return maximum `30` notifications.

DELETE
-
####`/api/v1/notifications/{notificationId}`####

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|204|success|
|400|invalid id|
|403|user is not authorized to delete the notification|
