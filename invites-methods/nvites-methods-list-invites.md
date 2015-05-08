Get a list of the user’s previous invites.

HTTP method: GET /services/v1/invites
Client authorization: no
User authorization: required
TLS: required

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/invites?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q

Example response
        {`
``  ``"success"``:``true``,``
``  ``"invites"``:``[``
``     ``{``
``        ``"email"``:``"jacinto+fooball@thrillist.com"``,``
``        ``"status"``:``"sent"``
``     ``}``
``  ``]``
``}`