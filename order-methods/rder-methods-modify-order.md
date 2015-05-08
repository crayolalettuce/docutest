Order mod


HTTP method: POST /services/v1/orders/<id>/modify
Client authorization: No
User authorization: Required
TLS: Required


**Required Parameters:**

order_id - integer Order ID
action - string "recalculate" or "cancel"
mode - string "simulate" or "execute"
address - object Address
    company

    address

    address2

    city

    state

    zip

    country

    phone

    validate - boolean

    status

items - empty if all items are to be removed otherwise option id => qty of items remaining in the order
cancel_reason_id - integer Cancel Reason


**Response:**

message - string Success or error message
order - object Order Info - See Get Order for format
canceled - boolean
executed - boolean
shipping_exclusions - boolean
address_valid - boolean


**Example Request:**

        curl -kd "oauth_token=ea5d78e5f16a5873689789f99d05b8f7&action=recalculate&mode=simulate&order_id=1610000&address%5Bfirst_name%5D=Kamran&address%5Blast_name%5D=Khawaja&address%5Bcompany%5D=&address%5Baddress%5D=568 Broadway&address%5Baddress2%5D=&address%5Bcity%5D=New York&address%5Bstate%5D=NY&address%5Bzip%5D=10012&address%5Bcountry%5D=US&address%5Bphone%5D=1234567890&address%5Bvalidate%5D=false&items=&cancel_reason_id=" "https://jackthreads.dev:7443/services/v1/orders/1610000/modify?oauth_token=ea5d78e5f16a5873689789f99d05b8f7"


**Example Response:**


        {
          "**success**":true,
          "**message**":"Your credit card will not be charged for this order.",
          "**order**":{
            "**id**":1610000,
            "**total**":"77.95",
            "**giftcard_payment**":"0.00",
            "**created**":"2013-04-24 12:25:15",
            "**status**":"created",
            "**saved**":"69.00",
            "**retail**":"165.00",
            "**items**":[
              {
                "**option_id**":426057,
                "**option**":{
                  "**id**":429448,
                  "**sku**":"JT00429448",
                  "**color**":{
                    "**id**":1212,
                    "**code**":null,
                    "**name**":"Blue Onyx"
                  },
                  "**size**":{
                    "**id**":65,
                    "**code**":"36",
                    "**name**":"36"
                  }
                },
                "**qty**":1,
                "**price**":"18.00",
                "**name**":"Printed Tank"
              },
              {
                "**option_id**":429448,
                "**option**":{
                  "**id**":429448,
                  "**sku**":"JT00429448",
                  "**color**":{
                    "**id**":1212,
                    "**code**":null,
                    "**name**":"Blue Onyx"
                  },
                  "**size**":{
                    "**id**":65,
                    "**code**":"36",
                    "**name**":"36"
                  }
                },
                "**qty**":3,
                "**price**":"26.00",
                "**name**":"Basic Short"
              }
            ],
            "**subtotal**":"96.00",
            "**discount**":"24.00",
            "**tax**":"0.00",
            "**shipping_cost**":"5.95",
            "**tracking_nr**":null,
            "**shipping**":{
              "**method**":null,
              "**carrier**":null,
              "**first_name**":"Kamran",
              "**last_name**":"Khawaja",
              "**address**":"568 Broadway",
              "**address2**":"",
              "**city**":"New York",
              "**state**":"NY",
              "**zip**":"10012",
              "**country**":"US",
              "**shipping_carrier**":"usps",
              "**shipping_method**":"USPR",
              "**pretty_dates**":{
                "**created_FdY**":"",
                "**created_ndY**":"",
                "**delivery_FdY**":{
                  "**start**":"May 01, 2013",
                  "**end**":"May 08, 2013",
                  "**date**":""
                },
                "**delivery_ndY**":{
                  "**start**":"5\/01\/2013",
                  "**end**":"5\/08\/2013",
                  "**date**":""
                }
              }
            },
            "**currency**":{
              "**code**":"EUR",

              "**symbol**":"€",
              "**name**":"Euro",

              "**locale**":"FR"
            },

            "**payment**":{
              "**type**":"VISA",
              "**last_four**":"1111"
            }
          },
        
  "**canceled**":true,
  "**executed**":false,
  "**shipping_exclusions**":false,
  "**address_valid**":true
        }