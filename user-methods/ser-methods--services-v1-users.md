HTTP method: POST /services/v1/users
Client authorization: required
User authorization: no
TLS: required

Required parameter
method        - string Method of signup. Possible values are: "email" (normal email/pass signup), "google" (Google+ signup)


Required parameters for Email signup
 email  - string Email address
 password - string Password (It is possible to omit this parameter and have the API create a password and include it in the welcome email. If your implementation requires this feature, please ask for details)
 zip          - string Postal code


Required parameters for Google signup
 google_access_token  - string Access token provided by Google

Optional parameters

 first_name  - string First name
 last_name  - string Last name
 gender   - string Gender; “M” - male, “F” - female; defaults to “M”
 daily_newsletter - boolean True if the user opts-in to the daily email
 is_21   - boolean True if the user is 21 years old or older
 approve          - boolean If true, approve the user (default: false)
        landing_page_id  - integer Landing page ID, for tracking sources of sign-ups
        source  - string Source of sign-up (default: "api"), for internal tracking (maps to Zuul origin_type)
 origin_id - string Used for internal source tracking (maps to Zuul origin_id)
 partner - string Used for internal source tracking (maps to Zuul partner)
        sub_source  - string Free form sub source used for internal tracking
        sub_source_1 - string Free form sub source used for internal tracking (maps directly to Zuul sub_source_1)
        sub_source_2 - string Free form sub source used for internal tracking (maps directly to Zuul sub_source_2)
        login_token  - boolean If true, a login token will be returned which can be used to passively log the user into the website (this is not an oauth token)
       

**Response**

        success - boolean True if the user was created successfully, false on failure
        user                - object User info
                uid           - integer User ID
                first_name  - string First name
                last_name  - string Last name
                email   - string Email
                birthday          - string Birthday
                gender   - string Gender
                zip           - string Postal code
                username  - string Username
                subscriptions  - objects Email subscriptions


                **link           - string User invite URL**

                short_url          - string Shortened link for user's invite URL
                fb_connected         - boolean True or False if user's account is connected to FB
                post_to_fb         - string Whether or not the user has granted permissions to post on their behalf
                balance          - float User's opening account balance
                has_paypal         - boolean Whether or not the user has a PayPal account stored
                login_token  - string Login token. Only present if login_token was requested
                <strike>tl_uid</strike>   - integer (Deprecated; do not use) <strike>Thrillist user ID. This will be the same as uid</strike>
        default_edition    - object Suggested Default Edition
                id                             - integer
                name                       - string Name of the TL edition
                signup_header        - string Edition signup header
                signup_text             - string Edition signup text

Example request
        curl -k -d 'email=jacinto%2Bcu11%40thrillist.com&password=123456&zip=10012&oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://16.camp.jackthreads.com:9116/services/v1/users

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
     "link":"https:\/\/16.camp.jackthreads.com:9116\/invite\/JacintoShy1",**

** **"short_url":"http:\/\/thrl.st\/12HIgMh",
     "fb_connected":false,
     "post_to_fb":"-1",
     "balance":"0.00",
     "has_paypal":false,**

     "tl_uid":**899419,`
 "**login_token**":"5e02128c4df704df55592efce55970c1"
**  }**

**  , **"**default_edition**":{
            "**id**":1,
            "**name**":"New York",
            "**signup_header**":"Yes, sign me up for Thrillist New York.",
            "**signup_text**":"By the way, we see that you're in New York.  What a coincidence; our brother company, Thrillist, is too. Thrillist is a free daily email that uncovers the best new bars, restaurants, events, gear, and services in your 'hood.  Click below to get on the list and you'll also get exclusive weekly hookups and discounts from Thrillist Rewards -- otherwise continue your lonely, fruitless search for entertainment without us.  Your call."
          }**}**`