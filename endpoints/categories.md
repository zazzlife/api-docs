Categories
=
***This info hardly changes, so we recommend you to fetch all tags and store it everytime the app starts***

Path: `/api/v1/categories`

* Authorization header should be: `AuthToken <access_token>`

Available methods:

|Method|Description|
|------|-----------|
|GET|used for getting all or a single category|

GET
-
#####Getting all categories: `/api/v1/categories`#####

######Response: collection of [Category](https://github.com/zazzlife/api-docs/blob/master/objects/category.md)######

-----------------------

#####Getting a single category: `/api/v1/categories/{id}`#####

######Response: [category](https://github.com/zazzlife/api-docs/blob/master/objects/category.md)######
