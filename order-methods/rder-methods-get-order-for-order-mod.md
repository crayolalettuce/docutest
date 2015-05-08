Get details of a specific order along with some other information to modify the order.


HTTP method: GET /services/v1/orders/<id>/modify
Client authorization: No
User authorization: Required
TLS: Required


**Required Parameters:**

id - integer Order ID


**Response:**

order - object Order Info - See Get Order for format
can_modify - object
    shipping - boolean If shipping info can be modified

    items - boolean If items info can be modified
modifiable - boolean
item_list - object List of option ids and total qty for each
cancal_reasons - object List of possible reasons for canceling an order keyed on cancel_reason_id


**Example Request:**

        curl -k "https://jackthreads.dev:7443/services/v1/orders/1610000/modify?oauth_token=ea5d78e5f16a5873689789f99d05b8f7"


**Example Response:**


        {
          "**success**":true,
          "**errors**":[],
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
            "**payment**":{
              "**type**":"VISA",
              "**last_four**":"1111"
            }
          },
          "**can_modify**":{
            "**shipping**":true,
            "**items**":true,
            "**created**":"2013-04-24 12:25:21"
          },
          "**modifiable**":true,
          "**item_list**":{
            "**426057**":1,
            "**429448**":3
          },
          "**cancel_reasons**":{
            "**1**":"Accidental Purchase",
            "**2"**:"Duplicate Purchase",
            "**3**":"No longer want to wait",
            "**4**":"No longer want it"
          }
        }