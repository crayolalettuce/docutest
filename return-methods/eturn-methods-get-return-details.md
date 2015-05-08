Get details for a specific return.

HTTP method: GET /services/v1/returns/<id>
Client authorization: no
User authorization: required
TLS: required

Required parameters
 id - integer Return ID

Response
 return   - object Return info
  id   - integer Return ID
  order_id  - integer Order ID
  sku   - string SKU
  item_id   - integer Product option ID
  status   - string Status ...
  rma   - string RMA #
  receive_by  - string Date to receive by
  created  - string Return creation timestamp
  label_eligible  - boolean True if return is eligible for a label
  qty   - integer Quantity of returned items
  price   - string Price
  name   - string Product name
  reason   - object Return reason info
   id   - integer Return reason ID
   name   - string Return reason
  size   - object Size info
   id   - integer Size ID
   name   - string Size
   code   - string Size code

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/returns/10564?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q

Example response
        {`
``  ``"success"``:``true``,``
``  ``"return"``:``[``
``     ``{``
``        ``"id"``:``10564``,``
``        ``"order_id"``:``239740``,``
``        ``"sku"``:``"97514"``,``
``        ``"item_id"``:``87745``,``
``        ``"status"``:``"pending"``,``
``        ``"rma"``:``"RMA210564"``,``
``        ``"receive_by"``:``"2011-12-20"``,``
``        ``"created"``:``"2011-08-15 10:42:18"``,``
``        ``"label_eligible"``:``true``,``
``        ``"qty"``:``1``,``
``        ``"price"``:``"45.99"``,``
``        ``"name"``:``"Rehab Bloc Pant Taupe"``,``
``        ``"reason"``:``{``
``           ``"id"``:``7``,``
``           ``"name"``:``"Incorrect item delivered"``
``        ``}``,``
``        ``"size"``:``{``
``           ``"id"``:``125``,``
``           ``"name"``:``"Medium"``,``
``           ``"code"``:``"M"``
``        ``}``
``     ``}``
``  ``]``
``}`