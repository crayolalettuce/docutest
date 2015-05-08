**

## []()Caution
The JackThreads v1 API is under development, so parameters and responses are subject to change.

## []()Staging
We provide a staging site for development:

Host: 16.camp.jackthreads.com
Port: 9016
HTTPS port: 9116

## []()Meta
For each API method this documentation provides a short description of its functionality, a section describing how the method should be accessed, and five optional sections describing required parameters, optional parameters, response, example usage and example responses.

### []()Method access

HTTP method  - The HTTP method used (either “GET” or “POST”)
Client authorization - Whether client authorization is required (“required” or “no”)
User authorization - Whether user authorization is required (“required” or “no”)
TLS   - Whether TLS is required (“required” or “no”)
## []()Declarations
Responses are encoded in JSON format with a content-type of “application/json”. All methods responses include at least one field in a JSON document called “success”. The “success” field contains a boolean value that is true on success and false on error. Internal server errors results in undefined behavior, so testing for a true success value is encouraged. 
## []()Parameters
Some API methods accept parameters. These may be either required or optional. Parameters may come in the form of query parameters (e.g. ), HTTP POST parameters, or URI parameters (e.g. /).

## []()Access control
Note: access control is currently in-progress. To access API methods requiring user authorization, pass the user’s JackThreads user ID as the value to “oauth_token” in either the request body (for methods requiring an HTTP POST) or in the query part of the URL. The /services/v1/users/login method returns a suitable value that can be passed to oauth_token.

The JackThreads API uses [OAuth 2 draft 10](http://tools.ietf.org/html/draft-ietf-oauth-v2-10) for authentication. Clients are provided an ID and a secret that are required to access the API. This documentation uses “jackthreads” and “kobol” as the ID and secret, respectively. On each API request, the client MUST identify themselves by either HTTP basic authentication -- using the client ID and secret as username and password -- or by passing the client ID and secret as values to fields named “client_id” and “client_secret”, within the request body.

Certain API methods, like user registration (/services/v1/users), require client authorization. Client authorization is done by simply exchanging client credentials (id and secret) for an access token. E.g.:

        curl -k -d 'grant_type=none' https://jackthreads:kobol@16.camp.jackthreads.com:9116/services/v1/oauth/token

Other methods, like editing user information (/services/v1/user/edit), require user authorization. 

        curl -k -d 'grant_type=password&username=jacinto%2Bcu11%40thrillist.com&password=123456' https://jackthreads:kobol@16.camp.jackthreads.com:9116/services/v1/oauth/token

For more details, see /services/v1/oauth/token.**


**Internationalization**

**Request**

Parameters expected to be passed in to all requests:

**locale** - string Value accurately specifies the users location
**local_currency** - string AUD, CAD, USD, or 1 (use what JITR decides for this particular locale).  Use this to force USD for the specified locale
Some Sample Requests:

curl -sd "https://jitr.jackthreads.dev/services/v1/cart/full?oauth_token=8bbecaf92bdef8fbcdaca04f14f7a857&**locale**=fr&**local_currency**=eur"

curl -sd "https://jitr.jackthreads.dev/services/v1/cart/full?oauth_token=8bbecaf92bdef8fbcdaca04f14f7a857&**locale**=jp&**local_currency**=usd"



**Response**Response will include a currency object at the top level that specifies which currency should be used.  In some cases the currency object embedded inside an existing response object should override the top level object (In the case of [List Orders](jackthreads-v1-api-order-methods-list-orders), where each order will contain what currency was used).


All fields that reflect pricing in a response are returned in the currency specified by the currency object.


Sample Response indicates product price of €3*5*:
*{*
***success**: true,***product**: {
**id**: 12345,
**price**: 35},

***currency**: {*

***code**: "EUR",*

***symbol**: "€",*

***name**: "Euro",*

***locale**: "FR"*

*}**}
*