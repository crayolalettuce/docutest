Get a list of current sizes for the given category.

HTTP method: GET /services/v1/categories/<id>/sizes
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Category ID

Response
 sizes  - array List of sizes
  id  - integer Size ID
  name  - string Size

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/categories/2/sizes

Example response
        {`
``   ``"success"``:``true``,``
``   ``"sizes"``:``[``
``      ``{``
``         ``"id"``:``108``,``
``         ``"name"``:``"7 "``
``      ``}``,``
``      ``{``
``         ``"id"``:``117``,``
``         ``"name"``:``"7.5"``
``      ``}``,``
``      ``{``
``         ``"id"``:``118``,``
``         ``"name"``:``"8"``
``      ``}``
``   ``]``
``}`