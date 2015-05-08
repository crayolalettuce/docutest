Get a list of the user’s available credits.

HTTP method: GET /services/v1/credits
Client authorization: no
User authorization: required
TLS: required

Response
 credits  - array List of credits
  id  - integer Credit ID
  amount - string Credit amount
  expires - string Date of expiration
  desc  - string Description
  approved - boolean If true, credit is approved

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/credits?oauth_token=fb18fc25e7e41608dadddcf567e9fe22

Example response
        {`
``  ``"success"``:``true``,``
``  ``"credits"``:``[``
``     ``{``
``        ``"id"``:``944772``,``
``        ``"amount"``:``"20.00"``,``
``        ``"expires"``:``null``,``
``        ``"desc"``:``""``,``
``        ``"approved"``:``true``
``     ``}``
``  ``]``
``}`