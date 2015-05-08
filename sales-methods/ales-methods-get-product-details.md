Get product details in a given sale.

HTTP method: GET /services/v1/sales/<sale_id>/products/<product_id>?talent=true/false
Client authorization: no
User authorization: no
TLS: no

Required parameters

sale_id  - integer Sale ID
product_id - integer Product ID


Optional parameters

talent  - string whether return taleng info
         locale             - string 2 character country code for retrieving international prices
         replaceprice    - boolean true to replace the 'price' field of products instead of appending converted valuesResponse
    sale  - object Sale info
        id   - integer Sale ID
        name  - integer Sale name
        start_date - string Start date
        end_date  - string End date
    product - object Product details in the sale
        id   - integer Product ID
        brand  - object Brand info
            id       - integer Brand ID
            name      - string Brand name
        categories - array List of categories
            id - integer Category ID
            name - string Category name
        name   - string Product name
        desc   - string Product description
        features          - string Product features
**

talent   - object Model information (null if none available)**


**

 height   - string Models height
 weight   - string Model’s weight
 waist   - string Model’s waist size**

        weight   - string Product weight
        price   - string JackThreads price, or converted price if flag 'replaceprice' is passed.
        retail           - string Retail price, or converted price if flag 'replaceprice' is passed.
        converted_price - string JackThreads price in locale currency, default USD. Doesn't exist if flag 'replaceprice' is passed.
        converted_retail - string Retail price in locale currency, default USD. Doesn't exist if flag 'replaceprice' is passed.
        images   - array List of image URIs
        almost_sold_out    - boolean True if product is almost sold out
        sold_out - boolean True if product is sold out
        options  - array List of product options
            id           - integer Product option ID
            sku   - string SKU
            sold_out - boolean True if product option is sold out
            color   - object Color info
                id           - integer Color ID
                code   - string Color code
                name   - string Color name
            size   - object Size info
                id           - integer Size ID
                code   - string Size code
                name   - string Size name
    currency - object Currency information
        code  - string 3 char currency code (USD, JPY)
        symbol  - string UTF8 encoded currency symbol
        name  - object Name of currency (US Dollar, Euro)


Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/sales/2847/products/19687

Example response
        {`
``   ``"success"``:``true``,``
``   ``"sale"``:``{``
``      ``"id"``:``2847``,``
``      ``"name"``:``"Second Sunday"``,``
``      ``"start_date"``:``"2011-08-03 12:00:00"``,``
``      ``"end_date"``:``"2011-08-10 12:00:00"``
``   ``}``,``
``   ``"product"``:``{``
``      ``"id"``:``19687``,``
``      ``"name"``:``"Rehab Tao Pant Heather Navy"``,``
``      ``"desc"``:``"Rehab Tao Pant by Second Sunday. 100% Authentic Second Sunday merchandise.\r\n \r\nModel is wearing a size Medium (32-33)\r\n\r\nModel's measurements:\r\nHeight: 6'0\"\r\nWaist: 32\"\r\nWeight: 160"``,``
``      ``"features"``:``"Color: Heather Navy\r\nMaterial: 80% Cotton\/20% Polyester\r\nOrigin: USA\r\nFit: Harem fit \r\nSmall fits size 29-31\r\nMedium fits size 32-33\r\nLarge fits size 34-36\r\nXLarge fits size 36-38\r\n2XLarge fits size 38-40\r\n\r\nDrop crotch\r\nSweatpants material \r\nDrawstring \r\nPull tabs \r\nLegs are tight at bottom "``,``
``      ``"weight"``:``"2.0"``,``
``      ``"price"``:``"97500"``,``
``      ``"retail"``:``"100.00"``,``
``      ``"brand"``:``{``
``         ``"id"``:``411``,``
``         ``"name"``:``"Second Sunday"``
``      ``}``,`
        
      "categories":[
         {
            "id":2,
            "name":"Streetwear"
         },
         {
            "id":10,
            "name":"Jackets"
         },
      ],
``
      "**talent**":{"id":"57","name":"Alexander Gordienko","height":"5'11\"","weight":"155","waist":"31","body_type":"Athletic","chest":"40.00","shoulders":"6.00","arm_length":"24","neck_size":"14","hips":"39","suit_size":""
```
```
        }
```
``      ,``"images"``:``[``
``         "``http://16.camp.jackthreads.com:9016/data/products/``TaoPantHeatherNavyA.jpg"``,``
``         "``http://16.camp.jackthreads.com:9016/data/products/``TaoPantHeatherNavyB.jpg"``,``
``         "``http://16.camp.jackthreads.com:9016/data/products/``TaoPantHeatherNavyC.jpg"``
``      ``]``,``
``      ``"options"``:``[``
``         ``{``
``            ``"id"``:``87734``,``
``            ``"name"``:``"Second Sunday Rehab Tao Pant Heather Navy  S"``,``
``            ``"sku"``:``"97500"``,``
``            ``"color"``:``null``,``
``            ``"size"``:``{``
``               ``"id"``:``141``,``
``               ``"code"``:``"S"``,``
``               ``"name"``:``"Small"``
``            ``}``
``         ``}``,``
``         ``{``
``            ``"id"``:``87735``,``
``            ``"name"``:``"Second Sunday Rehab Tao Pant Heather Navy  M"``,``
``            ``"sku"``:``"97501"``,``
``            ``"color"``:``null``,``
``            ``"size"``:``{``
``               ``"id"``:``125``,``
``               ``"code"``:``"M"``,``
``               ``"name"``:``"Medium"``
``            ``}``
``         ``}``
``      ``]`
         `  "**talent_size**":"32"`
           `}``
``}`