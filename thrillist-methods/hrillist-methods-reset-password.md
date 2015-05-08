Reset the user’s Thrillist password.

HTTP method: POST /services/v1/thrillist/password_reset
Client authorization: required
User authorization: no
TLS: required

Required parameters
One of:

id - integer User ID
email - string User’s email address
Example request
        curl -k -d 'oauth_token=bf55420723d51253d5d23a665712b4cf&id=`67890``' https://16.camp.jackthreads.com:9116/services/v1/thrillist/password_reset`

Example response
        {`
``   ``"success"``:``true``
``}`