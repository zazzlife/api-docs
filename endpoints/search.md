Search
=

Path: `/api/v1/search`

Available methods:

|Method|Description|
|------|-----------|
|GET||

GET
-
#####`/api/v1/search?query={query}`#####

######Request parameters######

|Property Name|Type|Description|
|-------------|----|-----------|
|query|string|can be `username`, `clubname` or `full name`|

######Possible Responses:######
|HTTP Status Code|Reason|
|----------------|------|
|200|Collection of [SearchResult](https://github.com/zazzlife/api-docs/blob/master/objects/searchresult.md)|
|400|invalid search query|
