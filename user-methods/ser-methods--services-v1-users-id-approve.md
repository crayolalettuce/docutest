Approve a given user. The user must be approved before an access token may be retrieved using the user’s credentials.

HTTP method: POST /services/v1/users/<id>/approve
Client authorization: required
User authorization: no
TLS: required

Required parameters
 id  - integer User ID

Example request
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://16.camp.jackthreads.com:9116/services/v1/users/899419/approve

Example response
        {`
`` ``"success"``:``true``
``}`