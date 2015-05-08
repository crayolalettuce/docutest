#### **[]()
Get an OAuth access token.

HTTP method: POST /services/v1/oauth/token
Authorization: required

Required parameters
 grant_type - string Either “password” (for user authorization) or “none” (for client authorization)

Optional parameters
 username - string End-user username; required for the “password” grant type
 password - string End-user password; required for the “password” grant type
                                            or facebook token for auth_type=facebook
                                            or Google access token for auth_type=google
        auth_type        - string Valid values are "facebook" and "google" depending on the login method

Response
 access_token  - string JackThreads access token
 expires_in  - integer Expiration time
 scope   - string Scope (not currently used)

Errors

Example request
        curl -d 'grant_type=none' https://jackthreads:kobol@16.camp.jackthreads.com:9116/services/v1/oauth/token
        

        Example FB auth request:
curl -d 'grant_type=password&username=abc@mailinator.com&password=someFBtoken&auth_type=facebook' https://jackthreads:kobol@16.camp.jackthreads.com:9116/services/v1/oauth/token

Example response
        {`
``  ``"access_token"``:``"b97a978eb98f377b10503fa5279fadeb"``,``
``  ``"expires_in"``:1209600,``
``  ``"scope"``:``null``
``}`