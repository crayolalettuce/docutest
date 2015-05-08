Update the user’s Thrillist subscriptions.

HTTP method: POST /services/v1/thrillist/editions/subscribe
Client authorization: no
User authorization: required
TLS: required

Required parameters
 editions  - array List of edition IDs (integers) to subscribe the user to

Example request
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22&editions[0]=1' https://16.camp.jackthreads.com:9116/services/v1/thrillist/editions/subscribe

Example response
        {`
``   ``"success"``:``true``
``}`