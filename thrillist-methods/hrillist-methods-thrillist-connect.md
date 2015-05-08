Connect an existing Thrillist account with a new JackThreads account.

HTTP method: POST /services/v1/thrillist/connect
Client authorization: required
User authorization: no
TLS: required

Required parameters
 email   - string Email address
 password  - string Password

Optional parameters
 first_name  - string First name
 last_name  - string Last name
 zip   - string Postal code

Response
 user   - object User info
  uid   - integer User ID
  first_name  - string First name
  last_name  - string Last name
  email   - string Email
  birthday  - string Birthday
  gender   - string Gender
  zip   - string Postal code
  username  - string Username
  subscriptions  - objects Email subscriptions
   daily   - boolean If true, subscribe to daily emails
  tl_uid   - integer Thrillist user ID

Example request
        curl -k -d 'oauth_token=bf55420723d51253d5d23a665712b4cf&email=jacinto%2Bcu11%40thrillist.com&password=123456&zip=10012' https://16.camp.jackthreads.com:9116/services/v1/thrillist/connect

Example response
        {`
``"success"``:``true``,``
``"user"``:``{``
``   ``"uid"``:``899419``,``
``   ``"first_name"``:``"jacinto+cu11"``,``
``   ``"last_name"``:``""``,``
``   ``"email"``:``"jacinto+cu11@thrillist.com"``,``
``   ``"birthday"``:``null``,``
``   ``"gender"``:``"M"``,``
``   ``"zip"``:``"10012"``,``
``   ``"username"``:``"jacintocu11"``,``
``   ``"subscriptions"``:``{``
``      ``"daily"``:``true``
``   ``}``,``
``   ``"tl_uid"``:``7548666``
``}`