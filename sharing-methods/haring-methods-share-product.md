Get share info for the given product.

HTTP method: GET /services/v1/sales/<sale_id>/products/<product_id>/share
Client authorization: no
User authorization: no
TLS: no

Required parameters
 sale_id  - integer Sale ID
 product_id - integer Product ID

Response
 text - string Share text

url - string Share URL
Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/share/2847/products/19692/share

Example response
        {`
``  ``"success"``:``true``,``
``  ``"text"``:``"Yes, please! Rehab Steen Short Heather Navy on sale @JackThreads"``,``
``  ``"url"``:``"http:\/\/www.jackthreads.com\/sales\/2847\/products\/19692"``
``}`