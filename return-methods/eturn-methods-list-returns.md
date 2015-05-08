Get a list of the user’s returns.

HTTP method: GET /services/v1/returns
Client authorization: no
User authorization: required
TLS: required

Response
 returns   - array List of returns
  id   - integer Return ID
  status   - string Status
  rma   - string RMA #
  receive_by  - string Date to receive by
  created  - string Return creation timestamp
  label_eligible  - boolean True if return is eligible for a label

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/returns?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q

Example response
        {`
``  ``"success"``:``true``,``
``  ``"returns"``:``[``
``     ``{``
``        ``"id"``:``"10564"``,``
``        ``"status"``:``"pending"``,``
``        ``"rma"``:``"RMA210564"``,``
``        ``"receive_by"``:``"2011-12-20"``,``
``        ``"created"``:``"2011-08-15 10:42:18"``,``
``        ``"label_eligible"``:``true``
``     ``}``
``  ``]``
``}`