Register
-
***This request only requires you to pass the `AppId` and `Request Signature` in the `Authorization` Header***

**1. Send a `GET` request to `/api/v1/register`.**

Response:

|Property Name|Type|Description|
|-------------|----|-----------|
|requestId|integer (64bit)||
|token|string||
|expirationTime|DateTime||

example:

    {
      "requestId":7,
      "token":"CC35D3E171B3C1102E8A32F60A626B6997A92391E9EEDA874EEF6A0723CE1F6EE31C5109FBBCF5A07200A8A5A63447B16DB77FDDBDC41BC83DCB4EC22A2557B0",
      "expirationTime":"2013-06-08T12:55:11.8743813Z"
    }

**2. Open `/account/appregister?requestId={requestId}&token={token}` page on a browser. For `requestId` and `token` use the values you received in the previous step.**
* At this point we'll take care of registering the user. After a successful registeration we'll redirect user to `/account/appauthsuccess`

**3. Wait until user gets redirected to `/account/appauthsuccess` then read the contents of the page and consider the user logged in.**

Response:

|Property Name|Type|Description|
|-------------|----|-----------|
|userId|integer||
|accountType|enum|Possible values: (User, Club)|
|passwordSignature|string|use this signature in Authorization header|
|displayName|string||
|displayPhoto|[PhotoLinks](https://github.com/zazzlife/api-docs/blob/master/objects/PhotoLinks.md)||

example:

    {
      "userId":8,
      "accountType":"User",
      "passwordSignature":"7UeoUtefyJLpwrOgxFjR1Qyf+oo0/cDGAftSoBQssLxLmBLCE2dxpkv62Z7+RZ7+URmb2UMO6enwJofXLa+CKw==",
      "displayName":"testUser",
      "displayPhoto":{
        "verySmallLink":"http://localhost:17433/Images/placeholder.gif",
        "smallLink":"http://localhost:17433/Images/placeholder.gif",
        "mediumLink":"http://localhost:17433/Images/placeholder.gif",
        "originalLink":"http://localhost:17433/Images/placeholder.gif"
      }
    }

You should use the exact values of `userId` and `passwordSignature` in the `Authorization` for your next calls.
