Get a list of variable texts.

HTTP method: GET /services/v1/texts
Client authorization: no
User authorization: no
TLS: no

Response
 texts  - array List of variable texts
  id  - integer Text ID
  name  - string Text name

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/texts

Example response
        {`
``  ``"success"``:``true``,``
``  ``"texts"``:``[``
``     ``{``
``        ``"id"``:``1``,``
``        ``"name"``:``"system"``
``     ``}``
``  ``]``
``}`