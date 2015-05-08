Get a list of current products in the given category.

HTTP method: GET /services/v1/categories/<id>/products
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Category ID

Response
 category  - string Category info
  id   - string Category ID
  name   - string Category
 products  - array List of products
  id   - string Product ID
  name   - string Product name
  price   - string JackThreads price
  retail   - string Retail price
  desc   - string Description
  features  - string Features
  weight   - string Weight
  options   - array List of product options
   id  - string Product option ID
   sku  - string SKU
   color  - object Color info
    id  - string Color ID
    code  - string Color code
    name  - string Color

 size  - object Size info    id  - integer Size ID
    name  - string Size

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/categories/3/products

Example response
        {`
``   ``"success"``:``true``,``
``   ``"category"``:``{``
``      ``"id"``:``"3"``,``
``      ``"name"``:``"Skate, Surf, Snow"``
``   ``}``,``
``   ``"products"``:``[``
``      ``{``
``         ``"id"``:``32185``,``
``         ``"name"``:``"Pico Black Suede"``,``
``         ``"price"``:``"29.99"``,``
``         ``"retail"``:``"58.00"``,``
``         ``"desc"``:``""``,``
``         ``"features"``:``""``,``
``         ``"weight"``:``"3.0"``,``
``         ``"options"``:``[``
``            ``{``
``               ``"id"``:``151338``,``
``               ``"sku"``:``"JT00151338"``,``
``               ``"color"``:``{``
``                  ``"id"``:``3692``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Black Suede"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``108``,``
``                  ``"code"``:``"7 "``,``
``                  ``"name"``:``"7 "``
``               ``}``
``            ``}``,``
``            ``{``
``               ``"id"``:``151339``,``
``               ``"sku"``:``"JT00151339"``,``
``               ``"color"``:``{``
``                  ``"id"``:``3692``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Black Suede"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``117``,``
``                  ``"code"``:``"7.5"``,``
``                  ``"name"``:``"7.5"``
``               ``}``
``            ``}``
``         ``"sale"``:``{``
``            ``"id"``:``3594``,``
``            ``"name"``:``"Lakai"``,``
``            ``"start_date"``:``"2011-09-11 12:00:00"``,``
``            ``"end_date"``:``"2011-09-19 12:00:00"``
``         ``}``
``      ``}``
``   ``]``
``}`