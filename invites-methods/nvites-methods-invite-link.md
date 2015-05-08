Get a user’s unique invite link

HTTP method: GET /services/v1/invites/link
Client authorization: no
User authorization: required
TLS: required

Response
 link - string URI

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/invites/link?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q

**Example response**

        {`
``  ``"success"``:``true``,``
``  ``"link"``:``"https:\/\/16.camp.jackthreads.com:9116\/invite\/JacintoShy1"``
``}`