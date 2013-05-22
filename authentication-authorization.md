Authentication And Authorization
=

For securing the API we'll be using HMAC based authorization. You will need to include the `Date` and `Authorization` HTTP headers.

Date Header
-
This doesn't need much explaining. The Date value should be in [RFC1123](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.18) format and not greater than `UtcNow()` and not less than `UtcNow() -1 minute`

Example: `Date: Wed, 22 May 2013 18:27:49 GMT`

Authorization Header
-

The scheme for the Authorization Header Should be `ZazzApi`.
For almost all calls you need to provide 4 parameters in the Authorization Header:

1. The Application Id that is given you followed by a `:`
2. Signature of the request followed by a `:` (Signing the request is explained below)
3. User Id which will be given to you after a successful login followed by a `:`
4. Hash of the user password. (You can find more details below)

The format will be `ZazzApi AppId:RequestSignature:UserId:PasswordHash`
