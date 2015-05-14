Majors
=
***This info hardly changes, so we recommend you to fetch all majors and store it everytime the app starts***

Path: `/api/v1/majors`

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting all or a single major|

GET
-
#####Getting all majors: `/api/v1/majors`#####

######Response: collection of [Major](https://github.com/zazzlife/api-docs/blob/master/objects/major.md)######

-----------------------

#####Getting a single major: `/api/v1/majors/{id}`#####

######Response: [Major](https://github.com/zazzlife/api-docs/blob/master/objects/major.md)######
