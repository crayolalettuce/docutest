Remove the given shipping address.

HTTP method: POST /services/v1/shipping/<id>/remove
Client authorization: no
User authorization: required
TLS: required

Required parameters
 id - integer Shipping address ID

Example request
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22q' https://16.camp.jackthreads.com:9116/services/v1/shipping/118243/remove

Example response
        {`
``  ``"success"``:``true``
``}`