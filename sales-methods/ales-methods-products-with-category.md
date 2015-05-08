Get products in a sale, within the given category.

HTTP method: GET /services/v1/sales/<sale_id>/categories/<category_id>
Client authorization: no
User authorization: no
TLS: no

Required parameters

sale_id  - integer Sale ID
category_id - integer Category ID


**Optional parameters
 sort  - string Sort parameter (either “natural”, “sold” or “price”) (default: “natural”)
 order  - string Sort order (either “asc” or “desc”) (default: “asc”)**

**

        offset - integer Offset, for pagination (first page is "0")

        limit - integer Limit, for pagination**

**

**Response

category  - object Category info
id   - integer Category ID
name   - string Category name
sale   - object Sale info
id   - integer Sale ID
name   - string Sale name
start_date  - string Start date
end_date  - string End date
brands   - array List of brand info
 id   - integer Brand ID
 name   - string Brand name
sizes   - array List of size info
 id   - integer Size ID
 name   - string Size
products  - array List of products in the sale
id   - integer Product ID
name   - string Product name
price   - string JackThreads price
retail   - string Retail price
image   - string Image URI
sold_out  - boolean True if the product is sold out
brand   - object Brand info
id   - integer Brand ID
name   - string Brand name
**

talent   - object Model information (null if none available)
 height   - string Models height
 weight   - string Model’s weight
 waist   - string Model’s waist size**

categories - array List of categories
     id - integer Category ID
     name - string Category name
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
Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/sales/3595/categories/1

Example response
        {`
``   ``"success"``:``true``,``
``   ``"category"``:``{``
``      ``"id"``:``"6"``,``
``      ``"name"``:``"Shirts"``
``   ``}``,``
``   ``"sale"``:``{``
``      ``"id"``:``3835``,``
``      ``"name"``:``"Bonafide "``,``
``      ``"start_date"``:``"2011-10-26 12:00:00"``,``
``      ``"end_date"``:``"2011-10-31 12:00:00"``,``
``      ``"image"``:``null``,``
``      ``"brands"``:``[``
``         ``{``
``            ``"id"``:``549``,``
``            ``"name"``:``"Bonafide"``
``         ``}``
``      ``]``,``
``      ``"sizes"``:``[``
``         ``{``
``            ``"id"``:``"141"``,``
``            ``"name"``:``"Small"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"125"``,``
``            ``"name"``:``"Medium"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"122"``,``
``            ``"name"``:``"Large"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"148"``,``
``            ``"name"``:``"X Large"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"28"``,``
``            ``"name"``:``"XX Large"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"80"``,``
``            ``"name"``:``"XXX Large"``
``         ``}``
``      ``]``
``   ``}``,``
``   ``"products"``:``[``
``      ``{``
``         ``"id"``:``27600``,``
``         ``"name"``:``"Colby L\/S Shirt Black\/Charcoal"``,``
``         ``"price"``:``"31.99"``,``
``         ``"retail"``:``"80.00"``,``
``         ``"images"``:``[``
``            "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BlackCharcoalPlaidBUShirtA.jpg"``,``
``            "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BlackCharcoalPlaidBUShirtB.jpg"``,``
``            "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BlackCharcoalPlaidBUShirtC.jpg"``
``         ``]``,``
``         ``"sold_out"``:``false``,``
``         ``"desc"``:``"Black\/Charcoal Plaid BU Shirt by Bonafide. 100% authentic Bonafide merchandise. \r\n\r\nModel is wearing a size Medium\r\n\r\nModel's Measurements: \r\nHeight: 5'11\"\r\nWaist: 32\"\r\nWeight: 170\r\n"``,``
``         ``"features"``:``"Color: Black\/Charcoal\r\nMaterial: 100% Cotton\r\nOrigin: China\r\nFit: True to Size\r\n\r\nButton Down Front\r\nDouble Breasted Flap Pockets\r\nCurved Shirt Tail\r\nDouble Button Barrel Cuff\r\n"``,``
``         ``"weight"``:``"0.7"``,``
``
 `        ``"categories"``:``[``
``            ``{``
``               ``"id"``:``6``,``
``               ``"name"``:``"Shirts"``
``            ``}``,``
``            ``{``
``               ``"id"``:``2``,``
``               ``"name"``:``"Streetwear"``
``            ``}``,``
``            ``{``
``               ``"id"``:``30``,``
``               ``"name"``:``"Button Ups"``
``            ``}``,``
``            ``{``
``               ``"id"``:``71``,``
``               ``"name"``:``"Woven"``
``            ``}``,``
``            ``{``
``               ``"id"``:``112``,``
``               ``"name"``:``"Shortsleeve"``
``            ``}``
``         ``]``,```         ``"brand"``:``{``
``            ``"id"``:``549``,``
``            ``"name"``:``"Bonafide"``
``         ``}``,``
``         ``"options"``:``[``
``            ``{``
``               ``"id"``:``129311``,``
``               ``"sku"``:``"JT00129311"``,``
``               ``"color"``:``{``
``                  ``"id"``:``2258``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Black\/Charcoal"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``141``,``
``                  ``"code"``:``"S"``,``
``                  ``"name"``:``"Small"``
``               ``}``
``            ``}``,``
``            ``{``
``               ``"id"``:``129316``,``
``               ``"sku"``:``"JT00129316"``,``
``               ``"color"``:``{``
``                  ``"id"``:``2258``,``
``                  ``"code"``:``null``,``
``                  ``"name"``:``"Black\/Charcoal"``
``               ``}``,``
``               ``"size"``:``{``
``                  ``"id"``:``80``,``
``                  ``"code"``:``"3XL"``,``
``                  ``"name"``:``"XXX Large"``
``               ``}``
``            ``}``
``         ``]``
``      ``}``
``   ]``
``}`