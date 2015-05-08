Get share info for the given sale.

HTTP method: GET /services/v1/sales/<id>/share
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Sale ID

Response
 text - string Share text

url - string Share URL
Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/share/2847/share

Example response
        {`
``  ``"success"``:``true``,``
``  ``"text"``:``"Yes, please! Second Sunday on sale @JackThreads"``,``
``  ``"url"``:``"http:\/\/www.jackthreads.com\/sales\/2847"``
``}`