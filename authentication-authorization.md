Authentication And Authorization
=

For securing the API we'll be using HMAC based authorization. You need to include the `Date` and `Authorization` HTTP headers.

Date Header
-
This doesn't need much explaining. The Date value should be in [RFC1123](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.18) format, not greater than `UtcNow()` and not less than `UtcNow() -1 minute`

Example: `Date: Wed, 22 May 2013 18:27:49 GMT`

Authorization Header
-

The scheme for the Authorization Header Should be `ZazzApi`.
For almost all calls you need to provide 4 parameters in the Authorization Header:

1. The Application Id that is given to you followed by a `:`
2. Signature of the request followed by a `:` (Signing the request is explained below)
3. User Id which will be given to you after a successful login followed by a `:`
4. Hash of the user password. (You can find more details below)

The format will be `ZazzApi AppId:RequestSignature:UserId:PasswordHash`

Example: `Authorization: ZazzApi 1:zgVMNvtvXoONhw3d4e4PfNzWowPiFIhyCTE6f3deRSS19iu8xkZ8ZAhZRQM0xJqzV3b3P709UFhK2/weYElVkA==:2:plXhubLyLT5LhEhM16qHehQqrf6z7Jgns8SPhNr6gAQvqUpbdWCgVDZ8ku+VFoU2LMjuPi/h1EfB9owzCXknSA==`

**Note:** There are few requests that you can exclude *UserId* and the *Password Signature* such as login request. Those requests are explicitly marked in the documentation. For all other requests you'll need to provide the full *Authorization* header.

Signing the request
-
You need to sign the following items using your application secret key for every request: `HTTP Verb`, `Date Header Value`, `Url Path` and `HTTP Body` if available.

1. Get the `UTF8` encoding value of these strings.
2. Sign it using `HMAC-SHA512` algorithm with your secret key.
3. Convert the hash to a base64 string.

Example:

    Signature = Base64(HMAC-SHA512(UTF8-Encoding(HttpVerb + "\n" +
                                                      Date + "\n" +
                                                      UrlPath + "\n" +
                                                      body)))
                                                      
                                                      
Signing the password
-
This process is very similar to signing the request:

1. Get the `UTF8` encoding value of the password.
2. Sign it using `HMAC-SHA512` algorithm with your secret key.
3. Convert the hash to a base64 string.
 
###Here's a complete HTTP Header example:###

    GET /api/v1/login HTTP/1.1
    Host: test.zazzlife.com
    Accept: application/json
    Date: Wed, 22 May 2013 18:27:49 GMT
    Authorization: ZazzApi 1:zgVMNvtvXoONhw3d4e4PfNzWowPiFIhyCTE6f3deRSS19iu8xkZ8ZAhZRQM0xJqzV3b3P709UFhK2/weYElVkA==:2:plXhubLyLT5LhEhM16qHehQqrf6z7Jgns8SPhNr6gAQvqUpbdWCgVDZ8ku+VFoU2LMjuPi/h1EfB9owzCXknSA==

