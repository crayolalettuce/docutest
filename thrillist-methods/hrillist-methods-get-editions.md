Get a list of Thrillist editions.

HTTP method: GET /services/v1/thrillist/editions
Client authorization: no
User authorization: no
TLS: no

Response

editions  - array List of editions
name   - string Edition name
id   - integer Edition ID
lng   - float WGS 84 longitude in degrees
lat   - float WGS 84 latitude in degrees
active   - boolean True if edition is active
coming_soon  - boolean True if edition is not active, but coming soon
Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/thrillist/editions

Example response
        {`
``   ``"success"``:``true``,``
``   ``"editions"``:``[``
``      ``{``
``         ``"name"``:``"Atlanta"``,``
``         ``"id"``:``10``,``
``         ``"lng"``:``-84.39``,``
``         ``"lat"``:``33.755``,``
``         ``"active"``:``true``,``
``         ``"coming_soon"``:``false``
``      ``}``,``
``      ``{``
``         ``"name"``:``"Detroit"``,``
``         ``"id"``:``38``,``
``         ``"lng"``:``-83.056640625``,``
``         ``"lat"``:``42.3260624446``,``
``         ``"active"``:``false``,``
``         ``"coming_soon"``:``true``
``      ``}``,``
``      ``{``
``         ``"name"``:``"New York"``,``
``         ``"id"``:``1``,``
``         ``"lng"``:``-73.99077``,``
``         ``"lat"``:``40.73464``,``
``         ``"active"``:``true``,``
``         ``"coming_soon"``:``false``
``      ``}``
``   ``]``
``}`