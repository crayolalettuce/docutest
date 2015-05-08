Get the featured item. The sale will have one or more items.

HTTP method: GET
Client authorization: no
User authorization: no
TLS: no

Response

sale   - object Sale info
 id   - string Sale ID
 name   - string Sale name
 start_date  - string Start date
 end_date  - string End date
 sizes  - array List of sizes
 id  - integer Size ID
        name - string Size
 brands  - array List of brands
 id  - integer Brand ID
        name - string Brand name
 image  - string Image
        products  - object Product details in the sale
id   - integer Product ID
brand   - object Brand info
 id   - integer Brand ID
        name  - string Brand name
name   - string Product name
sku   - string SKU
price   - string JackThreads price
retail   - string Retail price
images   - array List of image URIs
weight   - string Weight
desc   - string Description
features  - string Features
sold_out  - boolean If sold out, true
almost_sold_out - boolean If almost sold out, true
type   - string Sale type
options   - array List of product options
 id   - string Product option ID
 sku   - string SKU
 color   - object Color info
  id   - string Color ID
  code   - string Color code
  name   - string Color
 size   - object Size info
  id   - string Size ID
  name  - string Size
Example request
        curl http://jackthreads:kobol@16.camp.jackthreads.com:9016/services/v1/sales/featured_item

Example response
        {`
``   ``"success"``:``true``,``
``   ``"sale"``:``{``
``      ``"id"``:``4041``,``
``      ``"name"``:``"I am stylish"``,``
``      ``"start_date"``:``"2011-11-02 12:00:00"``,``
``      ``"end_date"``:``"2011-11-06 12:00:00"``,``
``      ``"image"``:``{``
``         ``"id"``:``"90429"``,``
``         ``"product_id"``:``"35482"``,``
``         ``"color_id"``:``"3803"``,``
``         ``"filename"``:``"SportChukkaShoeBrownD.jpg"``,``
``         ``"ordinal"``:``"4"``
``      ``}``,``
``      ``"brands"``:``[``
``         ``{``
``            ``"id"``:``168``,``
``            ``"name"``:``"Penguin Footwear"``
``         ``}``
``      ``]``,``
``      ``"sizes"``:``[``
``         ``{``
``            ``"id"``:``"118"``,``
``            ``"name"``:``"8"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"119"``,``
``            ``"name"``:``"8.5"``
``         ``}``,``
``         ``{``
``            ``"id"``:``"8"``,``
``            ``"name"``:``"13"``
``         ``}``
``      ``]``,``
``      ``"products"``:``[``
``         ``{``
``            ``"id"``:``35482``,``
``            ``"name"``:``"Sport Chukka Brown"``,``
``            ``"price"``:``"79.99"``,``
``            ``"retail"``:``"110.00"``,``
``            ``"images"``:``[``
``               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/SportChukkaShoeBrownA.jpg"``,``
``               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/SportChukkaShoeBrownB.jpg"``,``
``               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/SportChukkaShoeBrownC.jpg"``,``
``               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/SportChukkaShoeBrownD.jpg"``
``            ``]``,``
``            ``"sold_out"``:``true``,``
``            ``"almost_sold_out"``:``true``,``
``            ``"desc"``:``"Sport Chukka by Penguin Footwear. 100% Authentic Penguin Footwear merchandise.\r\n\r\nSize Shown: 10"``,``
``            ``"features"``:``"Color: Brown\r\nMaterial: Suede\r\nOrigin: China\r\nFit: True to size\r\nSuede Upper\r\nLeather Piping Detail on Upper\r\nContrast Stitching\r\nMan-Made Rubber Sole with Logo Detail\r\nLightly Cushioned Man-Made Footbed\r\nImported"``,``
``            ``"weight"``:``"0.0"``,``
``            ``"categories"``:``[``
``               ``{``
``                  ``"id"``:``1``,``
``                  ``"name"``:``"Contemporary"``
``               ``}``,``
``               ``{``
``                  ``"id"``:``115``,``
``                  ``"name"``:``"Mid"``
``               ``}``
``            ``]``,``
``            ``"brand"``:``{``
``               ``"id"``:``168``,``
``               ``"name"``:``"Penguin Footwear"``
``            ``}``,``
``            ``"options"``:``[``
``               ``{``
``                  ``"id"``:``165292``,``
``                  ``"sku"``:``"JT00165292"``,``
``                  ``"color"``:``{``
``                     ``"id"``:``3803``,``
``                     ``"code"``:``null``,``
``                     ``"name"``:``"Brown"``
``                  ``}``,``
``                  ``"size"``:``{``
``                     ``"id"``:``118``,``
``                     ``"code"``:``"8"``,``
``                     ``"name"``:``"8"``
``                  ``}``
``               ``}``,``
``               ``{``
``                  ``"id"``:``165299``,``
``                  ``"sku"``:``"JT00165299"``,``
``                  ``"color"``:``{``
``                     ``"id"``:``3803``,``
``                     ``"code"``:``null``,``
``                     ``"name"``:``"Brown"``
``                  ``}``,``
``                  ``"size"``:``{``
``                     ``"id"``:``5``,``
``                     ``"code"``:``"11.5"``,``
``                     ``"name"``:``"11.5"``
``                  ``}``
``               ``}``,``
``               ``{``
``                  ``"id"``:``165300``,``
``                  ``"sku"``:``"JT00165300"``,``
``                  ``"color"``:``{``
``                     ``"id"``:``3803``,``
``                     ``"code"``:``null``,``
``                     ``"name"``:``"Brown"``
``                  ``}``,``
``                  ``"size"``:``{``
``                     ``"id"``:``6``,``
``                     ``"code"``:``"12"``,``
``                     ``"name"``:``"12"``
``                  ``}``
``               ``}``,``
``               ``{``
``                  ``"id"``:``165301``,``
``                  ``"sku"``:``"JT00165301"``,``
``                  ``"color"``:``{``
``                     ``"id"``:``3803``,``
``                     ``"code"``:``null``,``
``                     ``"name"``:``"Brown"``
``                  ``}``,``
``                  ``"size"``:``{``
``                     ``"id"``:``8``,``
``                     ``"code"``:``"13"``,``
``                     ``"name"``:``"13"``
``                  ``}``
``               ``}``
``            ``]``
``         ``}``
``      ``]``,``
``      ``"type"``:``"util"``
``   ``}``
``}`