List products, on sale, in the given department.

HTTP method: GET
Client authorization: no
User authorization: no
TLS: no
Optional Parameters

         locale - string 2 character country code for retrieving international prices
        replaceprice - boolean true to replace the 'price' field of products instead of appending converted valuesResponse
 department  - objects Department info
  id   - string Department ID
  name   - string Department
  EUC   - string EUC
 products  - array List of products

id   - integer Product ID
name   - string Product name
price   - string JackThreads price
retail   - string Retail price
image   - string Image URI
sold_out  - boolean True if the product is sold out
brand   - object Brand info
id   - integer Brand ID
name   - string Brand name
options   - array List of product options
 id   - integer Product option ID
 sku   - string SKU
 color   - object Color info
  id   - integer Color ID
  code   - string Color code
  name   - string Color name
 size   - object Size info
  id   - integer Size ID
  code   - string Size code
  name   - string Size name
sale   - object Sale info
 id   - integer Sale ID
 name   - string Sale name
 start_date  - string Start time
 end_date  - string End time
Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/departments/1/products

Example response
        {`
``   ``"success"``:``true``,``
``   ``"department"``:``{``
``      ``"id"``:``1``,``
``      ``"name"``:``"Accessories"``,``
``      ``"weight"``:``0``,``
``      ``"EUC"``:``"EUC-09020802"``
``   ``}``,``
``   ``"products"``:``[``
``      ``{``
``         ``"id"``:``35200``,``
``         ``"name"``:``"Ditto Beanie Black"``,``
``         ``"price"``:``"15.99"``,``
``         ``"retail"``:``"26.00"``,``
``         ``"images"``:``[``

``         ``]``,``
``         ``"sold_out"``:``true``,``
``         ``"desc"``:``"Ditto Beanie by Rhythm. 100% Authentic Rhythm merchandise."``,``
``         ``"features"``:``"Color: Black\r\nFit: One size"``,``
``         ``"weight"``:``"0.0"``,``
``         ``"brand"``:``{``
``            ``"id"``:``437``,``
``            ``"name"``:``"Rhythm"``
``         ``}``,``
``         ``"options"``:``[``
``            ``{``
``               ``"id"``:``163827``,``
``               ``"sku"``:``"JT00163827"``,``
``               ``"color"``:``{``
``                  ``"id"``:``6``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Black"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``140``,``
``                  ``"code"``:``"OS"``,``
``                  ``"name"``:``"One Size"``
``               ``}``
``            ``}``
``         ``]``,``
``         ``"sale"``:``{``
``            ``"id"``:``3838``,``
``            ``"name"``:``"Rhythm"``,``
``            ``"start_date"``:``"2011-10-25 12:00:00"``,``
``            ``"end_date"``:``"2011-10-28 12:00:00"``
``         ``}``
``      ``}``,``
``      ``{``
``         ``"id"``:``35202``,``
``         ``"name"``:``"Ditto Beanie Teal"``,``
``         ``"price"``:``"15.99"``,``
``         ``"retail"``:``"26.00"``,``
``         ``"images"``:``[``

``         ``]``,``
``         ``"sold_out"``:``true``,``
``         ``"desc"``:``"Ditto Beanie by Rhythm. 100% Authentic Rhythm merchandise."``,``
``         ``"features"``:``"Color: Teal\r\nFit: One size"``,``
``         ``"weight"``:``"0.0"``,``
``         ``"brand"``:``{``
``            ``"id"``:``437``,``
``            ``"name"``:``"Rhythm"``
``         ``}``,``
``         ``"options"``:``[``
``            ``{``
``               ``"id"``:``163829``,``
``               ``"sku"``:``"JT00163829"``,``
``               ``"color"``:``{``
``                  ``"id"``:``1075``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Teal"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``140``,``
``                  ``"code"``:``"OS"``,``
``                  ``"name"``:``"One Size"``
``               ``}``
``            ``}``
``         ``]``,``
``         ``"sale"``:``{``
``            ``"id"``:``3838``,``
``            ``"name"``:``"Rhythm"``,``
``            ``"start_date"``:``"2011-10-25 12:00:00"``,``
``            ``"end_date"``:``"2011-10-28 12:00:00"``
``         ``}``
``      ``}``
``   ]``
``}`