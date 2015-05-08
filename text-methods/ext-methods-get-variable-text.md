Get the given variable text.

HTTP method: GET /services/v1/texts/<id>
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Static text variable ID

Response
 text  - object Text info
  id  - integer Text ID
  tag  - string Tag
  name  - string Text name
  body  - string Text body

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/texts/1

Example response
        {`
``  ``"success"``:``true``,``
``  ``"text"``:``{``
``     ``"id"``:``1``,``
``     ``"name"``:``"system"``,``
``     ``"tag"``:``"system"``,``
``     ``"body"``:``"<b>Summer Savings<\/b><br>Free shipping on orders over $75"``
``  ``}``
``}`