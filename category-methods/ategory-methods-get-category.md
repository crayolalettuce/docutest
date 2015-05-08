Get category information.

HTTP method: GET /services/v1/categories/<id>
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Category ID


**Optional parameters**

        with_products - bool If a true value, include product details in response
        with_icon - bool If a true value, include icon image URI in response

        offset - integer Offset, for pagination when with_products is set (first page is "0")

        limit - integer Limit, for pagination when with_products is set

        locale - string 2 character country code for retrieving international prices
        replaceprice - boolean true to replace the 'price' field of products instead of appending converted values


Response
 category  - object Category info
    id   - integer Category ID
    name   - string Name
    icon - string (Included only if with_icon set) Icon image URI
    products - array (Included only if with_products set) List of products


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
        price   - string JackThreads price
        retail           - string Retail price
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


Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/categories/4

Example response
        {`
``  ``"success"``:``true``,``
``  ``"category"``:``{``
``        ``"id"``:``4``,``
``        ``"name"``:``"Tees and Tanks"``
``  ``}``
``}`
        

        Example request
curl http://16.camp.jackthreads.com:9016/services/v1/categories/5?with_products=1``
``
``
**Example response**

``

{
   "success":true,
   "category":{
      "id":5,
      "name":"Sweatshirts",
      "products":[
         {
            "id":54488,
            "name":"Benjamin Zip Up Stripe Fleece Hoodie Red",
            "price":"59.99",
            "retail":"140.00",
            "images":[
               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BenjaminStripeZipUpFleeceHoodieRedA.jpg",
               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BenjaminStripeZipUpFleeceHoodieRedB.jpg",
               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BenjaminStripeZipUpFleeceHoodieRedC.jpg",
               "http:\/\/16.camp.jackthreads.com:9016\/data\/products\/BenjaminStripeZipUpFleeceHoodieRedD.jpg"
            ],
            "sold_out":false,
            "almost_sold_out":false,
            "desc":"Benjamin Zip Up Stripe Fleece Hoodie Red by Zanerobe. 100% authentic Zanerobe merchandise. \r\n\r\nModel is wearing a size Medium. \r\n\r\n",
            "features":"Color: Red \r\nMaterial: 100% Cotton \r\nFit: True to size \r\nOrigin: China \r\nZip-up front \r\nDrawstring hood\r\nRibbed cuffs and hem\r\nKangaroo pockets",
            "weight":"1.0",
            "categories":[
               {
                  "id":1,
                  "name":"Contemporary"
               },
               {
                  "id":5,
                  "name":"Sweatshirts"
               },
               {
                  "id":23,
                  "name":"Zip Up"
               },
               {
                  "id":64,
                  "name":"Regular"
               }
            ],
            "brand":{
               "id":208,
               "name":"Zanerobe"
            },
            "talent":{
               "height":"6'1\"",
               "weight":"170",
               "waist":"32"
            },
            "options":[
               {
                  "id":211524,
                  "sku":"JT00211524",
                  "sold_out":false,
                  "color":{
                     "id":5,
                     "code":null,
                     "name":"Red"
                  },
                  "size":{
                     "id":141,
                     "code":"S",
                     "name":"Small"
                  }
               },
               {
                  "id":211527,
                  "sku":"JT00211527",
                  "sold_out":false,
                  "color":{
                     "id":5,
                     "code":null,
                     "name":"Red"
                  },
                  "size":{
                     "id":148,
                     "code":"XL",
                     "name":"X Large"
                  }
               }
            ]
         }
      ]
   }
}``