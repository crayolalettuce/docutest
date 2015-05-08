Get items in the user’s cart.

HTTP method: GET /services/v1/cart
Client authorization: no
User authorization: required
TLS: required


**Optional parameters**

    shipping_method - string Providing a shipping method causes tax and shipping costs to be calculated
    addressId - integer shipping address to calculate correct tax/customs/shipping. 

Response

success - boolean True if the cart was complied successfully
cart - object Cart info
qty - integer Number of items in the cart
expired - integer Number of expired items in the cart
subtotal - string Subtotal
shipping - string Shipping cost
customs - string Customs for international orders
tax - string Taxes (US or international VAT)
discount - string Discount for applied credits (this does not include promo reductions)
store_credit - string Discount for applied store credits
gift_card - string Amount of gift card credit applied to cart
coupon_discount - string Discount for coupons applied to cart
coupons - object Array of objects containing promo info
id - integer Promo ID
name - string Promo name
type - string Promo type ("cash", "percent", "freeship", "fixedprice", or "lowestcost")
method - string Either "manual" or "auto"
amount - string Promo discount amount
desc - string Description
show - boolean Whether or not this coupon should be shown in the cart summary
total - string Total price
retail - string Retail price
saved - string Amount saved
items - array List of items in the cart
id - integer Product option ID
sku - string SKU
cart_id - integer Cart ID
product_id - integer Product ID
name - string Name
expires - string Expiration time
price - string JackThreads price
image - string Image URI
url - string URL to product
brand - object Brand info
id - integer Brand ID
name - string Brand name
color - object Color info
id - integer Color ID
name - string Color name
size - object Size info
id - integer Size ID
name - string Size
sale - object Sale info
id - integer Sale ID
name - string Sale name
start_date - string Sale start time
end_date - string Sale end time
qty - integer Number of items
is_expired - boolean True if...
is_returnable - boolean If true, this item is returnable
is_virtual - boolean True if the item is a virtual product like a gift card
est_delivery - string Estimated delivery date range for the item
shop_id - string ID of the shop in which the item was addeddiscount_price - string Price of the item if it qualifies for a "higher in the funnel" discount

coupon_sale_id  - int If the item qualifies for a "higher in the funnel" discount, this is the sale_id it is using

estimated_delivery - string Estimated delivery of the cart as a whole

cart_expiration - string Timestamp of when the items in the cart expire

instock - int-bool 1/true if the whole cart is in-stock, 0/false if at least one item is presale
shipping_exclusions - array Any shipping exclusions that will prevent the order from completing, like not being able to ship to a certain country

has_exclusions - boolean True if there are exclusions (if there are no exclusions, shipping_exclusions will be null)

product_ids - array IDs of products which are excluded
message - array Message to the customer explaining why there are exclusions

formatted_summary - array List of objects summarizing the cost breakdown for the order

label - string Label for the line being described (e.g. Subtotal, Tax, Shipping, etc)

value - string Cost of each item with currency symbol (e.g. $19.00)
neg - boolean True if the value is a negative number (e.g. a discount), false if it is a positive number

formattedText - string Deprecated. Contains the same info as the summary except in a single string, the elements separated by a newline

time_now - int Unix timestamp of the current server time

Example request
        curl -k https://rc.jackthreads.com/services/v1/cart?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q

Example response





        {
          "success": true,
          "cart": {
            "qty": 1,
            "expired": 0,
            "subtotal": "32.00",
            "shipping": "0.00",
            "customs": "0.00",
            "tax": "0.00",
            "discount": "2.25",
            "store_credit": "2.25",
            "gift_card": "0.00",
            "coupon_discount": "8.00",
            "coupons": [
              {
                "id": 1,
                "name": "employee",
                "type": "percent",
                "method": "auto",
                "amount": "8.00",
                "desc": "Employee Discount",
                "show": true
              }
            ],
            "total": "21.75",
            "retail": "95.00",
            "saved": "63.00",
            "items": [
              {
                "id": 498738,
                "sku": "JT00498738",
                "cart_id": 25169623,
                "product_id": 142994,
                "name": "Slim Color Blocked Shirt with Gold Tie Bar",
                "expires": "2014-04-25 12:15:40",
                "price": "32.00",
                "image": "http://artemis-dev.thrillist.com/v1/image/1156689",
                "url": "/edge-by-wdny/shirts/button-ups/slim-color-blocked-shirt-with-gold-tie-bar/products/142994",
                "brand": {
                  "id": 1308,
                  "name": "EDGE by WD.NY"
                },
                "color": {
                  "id": 461,
                  "name": "White/Grey"
                },
                "size": {
                  "id": 122,
                  "name": "Large"
                },
                "sale": {
                  "id": 12802,
                  "name": "The Staple Shirt Shop",
                  "start_date": "2014-01-31 12:00:00",
                  "end_date": "2014-05-01 12:00:00"
                },
                "qty": 1,
                "is_expired": false,
                "is_returnable": true,
                "is_virtual": false,
                "est_delivery": "Wed 4/30/14 to Mon 5/5/14",
                "shop_id": "1"
              }
            ],
            "estimated_delivery": "Wed 4/30/14 to Mon 5/5/14",
            "cart_expiration": "2014-04-25 12:15:40",
            "instock": true,
            "shipping_exclusions": null,
            "formatted_summary": [
              {
                "label": "Subtotal",
                "value": "$32.00",
                "neg": false
              },
              {
                "label": "Employee Discount",
                "value": "$8.00",
                "neg": true
              },
              {
                "label": "Store Credit",
                "value": "$2.25",
                "neg": true
              },
              {
                "label": "Total",
                "value": "$21.75",
                "neg": false
              }
            ],
            "formattedText": "Subtotal: $32.00\nEmployee Discount: $8.00\nStore Credit: $2.25\nTotal: $21.75",
            "time_now": 1398441643
          }
        }