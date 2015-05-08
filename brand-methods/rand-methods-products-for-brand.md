Get products from a given brand.

HTTP method: GET /services/v1/brands/<id>/products
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id  - integer Brand ID


Optional parameters
        locale - string 2 character country code for retrieving international prices
        replaceprice - boolean true to replace the 'price' field of products instead of appending converted values

Response
 brand   - object Brand info
  id   - integer Brand ID
  name   - string Brand name
 products  - array List of products
  id   - integer Product ID
  name   - string Product name
  price   - string JackThreads price
  retail   - string Retail price
  desc   - string Description
  features  - string Features
  weight   - string Weight
  options   - array List of product options
   id   - integer Option ID
   sku   - string SKU
   color   - object Color info
    id   - integer Color ID
    name   - string Color
   size   - object Size info
    id   - integer Size ID
    code   - string Size code
    name   - string Size

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/brands/91/products

Example response
        {`
``   ``"success"``:``true``,``
``   ``"brand"``:``{``
``      ``"id"``:``"91"``,``
``      ``"name"``:``"Lira Clothing"``
``   ``}``,``
``   ``"products"``:``[``
``      ``{``
``         ``"id"``:``31932``,``
``         ``"name"``:``"Hazard Button Up Shirt"``,``
``         ``"price"``:``"19.99"``,``
``         ``"retail"``:``"49.99"``,``
``         ``"desc"``:``"Hazard Button Up Shirt by Lira Clothing. 100% authentic Lira Clothing merchandise. \r\n\r\nModel is wearing a size Large"``,``
``         ``"features"``:``"Color: Purple\r\nMaterial: 100% Cotton\r\nOrigin: India\r\nFit: True to Size"``,``
``         ``"weight"``:``"0.7"``,``
``         ``"options"``:``[``
``            ``{``
``               ``"id"``:``150158``,``
``               ``"sku"``:``"JT00150158"``,``
``               ``"color"``:``{``
``                  ``"id"``:``2342``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Purple"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``141``,``
``                  ``"code"``:``"S"``,``
``                  ``"name"``:``"Small"``
``               ``}``
``            ``}``,``
``            ``{``
``               ``"id"``:``150159``,``
``               ``"sku"``:``"JT00150159"``,``
``               ``"color"``:``{``
``                  ``"id"``:``2342``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Purple"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``122``,``
``                  ``"code"``:``"L"``,``
``                  ``"name"``:``"Large"``
``               ``}``
``            ``}``
``         ``]``,``
``         ``"sale"``:``{``
``            ``"id"``:``3549``,``
``            ``"name"``:``"Lira"``,``
``            ``"start_date"``:``"2011-09-13 12:00:00"``,``
``            ``"end_date"``:``"2011-09-16 12:00:00"``
``         ``}``
``      ``}``
``   ``]``
``}`