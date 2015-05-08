HTTP method: POST /services/v1/users/facebook/:fbAction
Client authorization: required
User authorization: not required for signup fbAction
TLS: required

Valid fbAction values:
signup, connect, disconnect, extend_permissions

Required parameters
 email   - string FB Email address
 fb_token  - string Facebook token

Optional parameters
        landing_page_id  - integer Landing page ID, for tracking sources of sign-ups
        sub_source  - string Free form sub source used for internal tracking



      


Responsesuccess
useruid   - integer User ID
first_name  - string First name
last_name  - string Last name
email   - string email
birthday  - string User’s birthdate (YYYY-MM-DD)
gender   - string Gender (“M” - male, “F” - female)
zip   - string Postal code
username  - string Username
subscriptions  - object Subscription info
daily   - boolean True if the user receives daily emaillink   - string User invite URL
short_url        - string Short URL version of the invite link
balance            - string Total amount of store credit + gift cards available to the user
paypal        - object
connected    - boolean True if the user has added a PayPal accountfacebook        - object
connected    - boolean True if the user has connected their FB account
post            - string See "Social Post Settings" below for values
id                - string FB UID; only present if connected is true
email        - string FB email; only present if connected is truegoogle            - object
connected    - boolean True if the user has connected their Google account
post            - string See "Social Post Settings" below for values
id                - string FB UID; only present if connected is true
email            - string Google email; only present if connected is true<strike>has_paypal</strike>    - boolean Deprecated; see paypal.connected above<strike>
fb_connected</strike> -  boolean Deprecated; see facebook.connected above
<strike>post_to_fb</strike> -  string Deprecated; see facebook.post above


**Social Post Settings**


* -1: Ask for publish_stream.  The user has never been asked
* 0: Do not ask for publish_stream permissions.  The user has already declined
* 1: Do not ask for publish_stream.  The user has already given us permission


Example request
        curl -skd 'oauth_token=a4ff8907e42272aa95097bb92ad1e2a9&fb_token=AAAFXaXAytMkBAMyRh0rziaeAHZA6gZAn3aIyEq7BEpsdXiaujxFXZCPwUKIBAokeiRZAGiMg3QjCqL08tOxX3YeiUTKGqXK3R88hIkajaU3FUaFZBY1ZA8&email=sdaasdfglaksfgl_ndhoclb_asdaasdfglaksfgl@tfbnw.net' 'https://jackthreads.dev:7443/services/v1/users/facebook/signup'

Example response


        { "**success**":true, "**user**":{ "**uid**":123456789, "**first_name**":"Matt", "**last_name**":"Doyle", "**email**":"matt@jackthreads.com", "**birthday**":null, "**gender**":"M", "**zip**":"", "**username**":"MattDoyle", "**subscriptions**":{ "**daily**":true }, "**link**":"https:\/\/rc.jackthreads.com\/invite\/MattDoyle", "**short_url**":"http:\/\/thrl.st\/XCBtCf", "**balance**":"20.00",  "**paypal**":{ "**connected**":true, },
         "**facebook**":{ "**connected**":true, "**post**":"-1", "**id**":"100006408460811", "**email**":"vvwrzys_seligsteinson_1374761988@tfbnw.net" }, "**google**":{ "**connected**":false, "**post**":"0" },
 "**has_paypal**":true,
 "**fb_connected**":true, "**post_to_fb**":"-1"` } }`