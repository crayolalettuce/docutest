HTTP method: GET /services/v1/users/wanted_products/:username
Client authorization: required
User authorization: no
TLS: required

Required parameters
    username - string 

Optional parameters
    offset     - int         Default 0

    limit        - int         Default 32

    sort        - string    Available options: created(date product was wanted), product, price, sold

    order      - string    Available options: asc or desc



      

**Response**

 products      - array List of wanted product ids


Example request
        curl -sk '`https://jackthreads.dev:7443/services/v1/users/wanted_products/kkhawaja?oauth_token=4624a66bf39ec16100b950162474869b`'


Example response

{ "success":true, "total_products":32, "products":[ { "id":65516, "shop_id":1, "name":"Walker Fur", "product_url":"\/shoe-the-bear\/footwear\/boots\/walker-fur\/products\/65516", "price":"119.00", "retail":"249.25", "clean_price":"119.00", "clean_retail":"249.25", "images":[ "http:\/\/ak-images.jackthreads.com\/v1\/image\/1127155" ], "desc":"Walker Fur by Shoe The Bear. 100% authentic Shoe The Bear merchandise.", "features":"Color: Black\r\nMaterial: Leather\r\nFit: True to size\r\nSize shown: 10\r\nLace-up front\r\nRubber sole\r\nStitching", "weight":"5.0", "brand":{ "id":1036, "name":"Shoe The Bear" }, "department":{ "id":3, "name":"Shoes" }, "sale":{ "id":"8780", "type":"in_stock_sellable" }, "color":{ "id":6, "name":"Black" }, "sold_out":false, "options":[ { "id":245525, "sku":"JT00245525", "upc":"000JT00245525", "color":{ "id":6, "name":"Black" }, "size":{ "id":118, "name":"8", "code":"8" }, "sold_out":false }, { "id":245526, "sku":"JT00245526", "upc":"000JT00245526", "color":{ "id":6, "name":"Black" }, "size":{ "id":119, "name":"8.5", "code":"8.5" }, "sold_out":false } ], "run_type":[ ], "categories":[ {
            "id": 2,

            "name": "Streetwear"

        },

        {
            "id": 10,

            "name": "Coats + Jackets"

        } ] } ], "list_details":{ "username":"kkhawaja" }, "filters":{ "sort":[ { "order":0, "id":"created", "name":"Date Added", "filter_parameter":"sort:created\/order:desc" }, { "order":1, "id":"newest", "name":"Newest", "filter_parameter":"sort:product\/order:desc" }, { "order":2, "id":"price_low", "name":"Price Low-to-High", "filter_parameter":"sort:price\/order:asc" }, { "order":3, "id":"price_high", "name":"Price High-to-Low", "filter_parameter":"sort:price\/order:desc" }, { "order":4, "id":"best_selling", "name":"Best Selling", "filter_parameter":"sort:sold\/order:desc" } ] } }


{ "success":true, "products":[
    '12345',

    '67890'

 ] }