List departments.

HTTP method: GET /services/v1/departments
Client authorization: no
User authorization: no
TLS: no

Response
 departments  - array List of departments
  id           - string Department ID
  name          - string Department

**                weight   - float Weight
  EUC   - string EUC**

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/departments

Example response
        {`
``   ``"success"``:``true``,``
``   ``"departments"``:``[``
``      ``{``
``         ``"id"``:``1``,``
``         ``"name"``:``"Accessories"``,``
``         ``"weight"``:``0``,``
``         ``"EUC"``:``"EUC-09020802"``
``      ``}``,``
``      ``{``
``         ``"id"``:``2``,``
``         ``"name"``:``"Apparel"``,``
``         ``"weight"``:``0``,``
``         ``"EUC"``:``"EUC-09050101"``
``      ``}``,``
``      ``{``
``         ``"id"``:``3``,``
``         ``"name"``:``"Shoes"``,``
``         ``"weight"``:``0``,``
``         ``"EUC"``:``"EUC-09050801"``
``      ``}``
``   ``]``
``}`