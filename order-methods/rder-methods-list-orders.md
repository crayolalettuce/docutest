Get a list of the user’s past orders.

HTTP method: GET /services/v1/orders
Client authorization: no
User authorization: required
TLS: required

Optional parameters
include_summary - boolean If true (1), response contains an array summarizing the cost breakdown for the order

**Response
**




order - object Order info


id - integer Order ID


created - string Order timestamp


total - string Total order value


giftcard_payment - string Amount of the order paid with one or more gift cards


status - string Order status


saved - string Amount saved


retail - string Retail amount


items - array List of items in the order


option_id - integer (DEPRECATED) Product option ID


name - string Product name


option - object Option info


id - integer Option ID


sku - string SKU


color - object Color info


id - integer Color ID


code - string Color code


name - string Color


size - object Size info


id - integer Size ID


code - string Size code


name - string Size


qty - integer Quantity


price - string Price


subtotal - string Subtotal


discount - string Discount


tax - string Tax


shipping_cost - string Shipping cost


tracking_nr - string Tracking number


shipping - object Shipping info


method - string Shipping method


carrier - string Shipping carrier


first_name - string First name


last_name - string Last name


address - string Address line 1


address2 - string Address line 2


city - string City


state - string State


zip - string Postal code


country - string Country (ISO 3166?)


payment - object Payment info


type - string Payment type (warning: may be null)


last_four - string Last four digits of the credit cardformatted_summary          - array List of objects summarizing the cost breakdown for the orderlabel          - string Label for the line being described (e.g. Subtotal, Tax, Shipping, etc)value         - string Cost of each item, which may be negative, with currency symbol (e.g. $19.00 or -$2.50)****



**

**



**Example request**

**curl -k https://rc.jackthreads.com/services/v1/orders?oauth_token=fb18fc25e7e41608dadddcf567e9fe22q&include_summary=1**

**

**

**Example response
        {
   "success":true,
   "orders":[
      {
         "id":452219,
         "total":"111.02",
         "created":"2011-11-25 10:37:22",
         "status":"created",
         "saved":"137.05",
         "retail":"237.00",
         "items":[
            {
               "option_id":135453,
               "option":{
                  "id":197902,
                  "sku":"JT00197902",
                  "color":{
                     "id":6759,
                     "code":"Leather",
                     "name":"Leather"
                  },
                  "size":{
                     "id":140,
                     "code":"OS",
                     "name":"One Size"
                  }
               },
               "qty":1,
               "price":"17.99",
               "name":""
            },
            {
               "option_id":197902,
               "option":{
                  "id":197902,
                  "sku":"JT00197902",
                  "color":{
                     "id":6759,
                     "code":"Leather",
                     "name":"Leather"
                  },
                  "size":{
                     "id":140,
                     "code":"OS",
                     "name":"One Size"
                  }
               },
               "qty":1,
               "price":"21.99",
               "name":"6 Oz. Genuine Leather Flask With Croco Design And Cigarette Case"
            }
         ],
         "subtotal":"137.44",
         "discount":"34.36",
         "tax":"7.94",
         "shipping_cost":"0.00",
         "tracking_nr":null,
         "shipping":{
            "method":null,
            "carrier":null,
            "first_name":"Jacinto",
            "last_name":"Shy",
            "address":"568 Broadway",
            "address2":"Suite 607",
            "city":"New York",
            "state":"NY",
            "zip":"10012",
            "country":"US"
         },
         "payment":{
            "type":null,
            "last_four":"6666"
         }
      }
   ]
}******