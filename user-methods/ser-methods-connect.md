Connects a user to a third party service.

HTTP method: POST /services/v1/users/connect
Client authorization: none
User authorization: required
TLS: required


Required parameters
 service  - string Valid values: "google"

Required parameters for Google
 access_token  - string Google user access token**

**

Optional parameters
        source  - string Free form sub source used for internal tracking



**Response**

 user                - object User info
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


Example request
        curl -kd 'oauth_token=a4ff8907e42272aa95097bb92ad1e2a9&service=google&access_token=AAAFXaXAytMkBAMyRh0rziaeAHZA6gZAn3aIyEq7BEpsdXiaujxFXZCPwUKIBAokeiRZAGiMg3QjCqL08tOxX3YeiUTKGqXK3R88hIkajaU3FUaFZBY1ZA8' 'https://rc.jackthreads.com/services/v1/users/connect'

Example response

{ "success":true, "user":{ "uid":5620203, "first_name":"qwerty", "last_name":"qwertyy", "email":"qwerty_ojvtrca_qwertyy@tfbnw.net", "birthday":null, "gender":"M", "zip":"", "username":"qwertyqwertyy", "subscriptions":{ "daily":true }, "link":"https:\/\/jackthreads.dev:7443\/invite\/qwertyqwertyy", } }