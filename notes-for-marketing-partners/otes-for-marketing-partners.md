Email this information to any marketing partners that wish to inject users into the Jackthreads (and not Thrillist) system.


**How to interface with the Jackthreads User API:**




Note that in all **TEST** instances you'll be communicating with stage1.jackthreads.com over SSL. So in the first example below, you'll send a POST request to https://stage1.jackthreads.com/services/v1/oauth.token.


Note that in all **LIVE** instances you'll be communicating with apipartner.jackthreads.com over SSL. So in the first example below, you'll send a POST request to https://apipartner.jackthreads.com/services/v1/oauth.token.


First, you need to get an OAuth token to be able to gain access to the API:


**Step 1:**

Get a username and password from JackThreads.  This currently has to be done manually by Tech.


**Step 2:**






#### **[]()
Get an OAuth access token.

HTTP method: POST /services/v1/oauth/token
Authorization: required

Required parameters
 grant_type - string “none” (for client authorization)

Response
 access_token  - string Access token
 expires_in  - integer Expiration time
 scope   - string Scope (not currently used)

Example request
        curl -d 'grant_type=none' \
         https://username:password@www.jackthreads.com/services/v1/oauth/token

Example response
        {`
``  ``"access_token"``:``"b97a978eb98f377b10503fa5279fadeb"``,``
``  ``"expires_in"``:1209600,``
``  ``"scope"``:``null``
``}`

**Step 3:**





Create a new user.

HTTP method: POST /services/v1/users
Client authorization: required


Required parameters
 email   - string Email address
 password  - string Password
 zip               - string Postal code

 source  - string "api", for internal tracking
 daily_newsletter - boolean true

Optional parameters
 first_name  - string First name
 last_name  - string Last name
 gender   - string Gender; “M” - male, “F” - female; defaults to “M”
 is_21   - boolean 1 if the user is 21 years old or older; 0 if they are under 21.
 approve - boolean true, otherwise, user will have to wait for approval before gaining site access
 landing_page_id - integer This is you assigned landing page ID. This is what Jackthreads uses to determine the source of the signup. 
    ^^ IF THIS IS WRONG OR MISSING, YOU WILL NOT BE COMPENSATED FOR THIS SIGNUP.
 sub_source - string Sub Source field used for internal tracking
       
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

**                link   - string User invite URL**  tl_uid   - integer Thrillist user ID

Example request
        curl -k -d 'email=jacinto%2Bcu11%40thrillist.com&password=123456&zip=10012&oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://www`.jackthreads.com/services/v1/users`

Example response
        
**{
  "success":true,
  "user":{
     "uid":899419,
     "first_name":"jacinto+cu11",
     "last_name":"",
     "email":"jacinto+cu11@thrillist.com",
     "birthday":null,
     "gender":"M",
     "zip":"10012",
     "username":"jacintocu11",
     "subscriptions":{
        "daily":true
     },
     "link":"https:\/\/stage1.jackthreads.com\/invite\/JacintoShy1",
     "tl_uid":7548666
  }
}**