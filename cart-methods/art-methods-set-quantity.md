Set the quantity for a given item in the user’s cart.

HTTP method: POST /services/v1/cart/set_qty
Client authorization: no
User authorization: required
TLS: required

Required parameters

**        sale_id  - integer Sale ID**

 qty  - integer Quantity
One of:
 sku  - string SKU
 option_id - integer Product option ID

Response
 cart  - object Cart info
  qty  - integer Number of items in the cart
  expired - integer Number of expired items in the cart
  subtotal - string Subtotal
  tax  - string Tax
  shipping - string Shipping cost
  discount - string Discount

                coupon - object Coupon and promo info


                    id - string Coupon ID

                    name - string Coupon name
                    type - string Discount type ("cash", "percent", "freeship", "fixedprice", or "lowestcost")
                    method - string Either "manual" or "auto"
                    amount - string Discount amount
                    desc - string Description  total  - string Total price
  retail  - string Retail price
  saved  - string Amount saved
  items  - array List of items in the cart
   id  - integer Product option ID
                        **product_id - integer Product ID**

   sku  - string SKU
   name  - string Name
   expires - string Expiration time
   price  - string JackThreads price
   image  - string Image URI
   brand  - object Brand info
    id  - integer Brand ID
    name  - string Brand name
   color  - object Color info
    id  - integer Color ID
    name  - string Color name
   size  - object Size info
    id  - integer Size ID
    name  - string Size
   sale  - object Sale info
    id  - integer Sale ID
    name  - string Sale name
    start_date - string Sale start time
    end_date - string Sale end time
   qty  - integer Number of items
   is_expired - boolean True if...
   is_returnable - boolean If true, this item is returnable
   ext_delivery - string If non-null, the item is subject to the listed extended delivery

**                        options  - array List of product option info
    id  - integer Option ID
    sku  - string SKU
    sold_out - boolean True if the option is sold out
    color  - object Color info
     id  - integer Size ID
     name  - string Color
    size  - object Size info
     id  - integer Size ID
     code  - string Size code
     name  - string Size**


Example request
        curl -k -d 'qty=2&option_id=87744&oauth_token=fb18fc25e7e41608dadddcf567e9fe22q' https://16.camp.jackthreads.com:9116/services/v1/cart/set_qty

Example response
        
{
   "success":true,
   "cart":{
      "qty":1,
      "expired":0,
      "subtotal":"80.99",
      "tax":"0.00",
      "shipping":"0.00",
      "discount":"0.00",
      "coupons":[
         {
            "id":71,
            "name":"Annie",
            "type":"percent",
            "method":"manual",
            "amount":"60.74",
            "desc":"mother ****"
         }
      ],
      "total":"0.00",
      "retail":"120.00",
      "saved":"39.01",
      "items":[
         {
            "id":191757,
            "sku":"JT00191757",
            "cart_id":2383595,
            "product_id":40826,
            "name":"Skytop",
            "expires":"2012-01-17 19:10:15",
            "price":"80.99",
            "image":"http:\/\/[www.jackthreads.com\/data\/products\/SkytopShoeBlackWhiteA_1.jpg](http://www.jackthreads.com//data//products//SkytopShoeBlackWhiteA_1.jpg)",
            "brand":{
               "id":21,
               "name":"Supra"
            },
            "color":{
               "id":2568,
               "name":"Black\/White"
            },
            "size":{
               "id":3,
               "name":"10.5"
            },
            "sale":{
               "id":4815,
               "name":"Hi-Top Shop",
               "start_date":"2012-01-13 12:00:00",
               "end_date":"2012-01-18 12:00:00"
            },
            "qty":1,
            "is_expired":false,
            "is_returnable":true,
            "est_delivery":"1\/27\/12",
            "options":[
               {
                  "id":191750,
                  "sku":"JT00191750",
                  "sold_out":true,
                  "color":{
                     "id":2568,
                     "name":"Black\/White"
                  },
                  "size":{
                     "id":108,
                     "code":"7 ",
                     "name":"7 "
                  }
               },
               {
                  "id":191763,
                  "sku":"JT00191763",
                  "sold_out":true,
                  "color":{
                     "id":2568,
                     "name":"Black\/White"
                  },
                  "size":{
                     "id":12,
                     "code":"14",
                     "name":"14"
                  }
               }
            ]
         }
      ]
   }
}