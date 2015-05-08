Get a list of available shipping methods, given items in the user’s cart.

HTTP method: GET /services/v1/shipping_methods
Client authorization: no
User authorization: required
TLS: required

**Optional parameters**

 addressId - integer Shipping Address ID

Response
 options   - array List of shipping methods
  country  - string Country
  shipmode  - string Ship mode
  name   - string Shipping method
  rate   - string Shipping rate

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/shipping_methods?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q

Example response
        {`
``  ``"success"``:``true``,``
``  ``"options"``:``[``
``     ``{``
``        ``"country"``:``"US"``,``
``        ``"shipmode"``:``"USPR"``,``
``        ``"name"``:``"USPS Mail"``,``
``        ``"rate"``:``"5.99"``
``     ``}``,``
``     ``{``
``        ``"country"``:``"US"``,``
``        ``"shipmode"``:``"USEM"``,``
``        ``"name"``:``"USPS Express Mail"``,``
``        ``"rate"``:``"25.95"``
``     ``}``,``
``     ``{``
``        ``"country"``:``"US"``,``
``        ``"shipmode"``:``"UGND"``,``
``        ``"name"``:``"UPS Ground"``,``
``        ``"rate"``:``"8.90"``
``     ``}``
``  ``]``
``}`