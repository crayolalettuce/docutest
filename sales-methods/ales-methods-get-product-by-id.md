Get a product by the product ID


**HTTP method**: GET /services/v1/products/<:id>

**Client authorization**: No
**User authorization**: No
**TLS**: No


Optional Parameters

         locale - string 2 character country code for retrieving international prices
        replaceprice - boolean  true to replace the 'price' field of products instead of appending converted values


**Response:**

*product: object** Product info*


id - int
name - string
desc - string
features - string
weight - string
price - string
retail - string
is_returnable - boolean
brand - object

id - int
name - string


department - object


id - int
name - string


images - array string
almost_sold_out - boolean
sold_out - boolean
est_delivery - string
talent - object

id - int
name - string
height - string
weight - string
waist - string


talent_size - string
options - array


id - string
sku - string
sold_out - boolean
color - object
id - stringcode - string
name - string
solid_color_group_id - int
solid_color_group_name - string
size - object
id - string
code - string
name - string
rank - string
department - string


categories - array
id - int
name - string
class_id - string
*sale: object Sale info*

id - int
name - string
start_date - string
end_date - string
*swatches: object Color Swatches keyed on Product ID*

sale_id - int
color_name - string
solid_color_name - string
hex_color - string
image - string
total_quantity - int


**Example Request:**

curl -s "http://jackthreads.dev:8080/services/v1/products/142566"


**Example Response:**


{
    "**success**": true,
    "**product**": {
        "**id**": 142566,
        "**name**": "Four Denim",
        "**desc**": "Four Denim by Cheap Monday. 100% authentic Cheap Monday merchandise.",
        "**features**": "Color: Rinse Black\r\nMaterial: 85% Cotton, 15% Polyester\r\nFit: True to size\r\n",
        "**weight**": "2.0",
        "**price**": "90",
        "**retail**": "90",
        "**is_returnable**": true,
        "**brand**": {
            "**id**": 135,
            "**name**": "Cheap Monday"
        },
        "**department**": {
            "**id**": 2,
            "**name**": "Clothing",
            "**slug**": "clothing"
        },
        "**images**": [
            "http:\/\/ak-images.jackthreads.com\/v1\/image\/1188967",
            "http:\/\/ak-images.jackthreads.com\/v1\/image\/1188968",
            "http:\/\/ak-images.jackthreads.com\/v1\/image\/1188969"
        ],
        "**almost_sold_out**": false,
        "**sold_out**": false,
        "**est_delivery**": "Mon 3\/24\/14 to Fri 3\/28\/14",
        "**talent**": {
            "**id**": 98,
            "**name**": "Beau Jensen",
            "**height**": "6'1\"",
            "**weight**": "165",
            "**waist**": "31"
        },
        "**talent_size**": "32",
        "**options**": [{
            "**id**": "497432",
            "**sku**": "JT00497432",
            "**sold_out**": false,
            "**color**": {
                "**id**": "16523",
                "**code**": "rinse blac",
                "**name**": "rinse black",
                "**solid_color_group_id**": "4",
                "**solid_color_group_name**": "Black"
            },
            "**size**": {
                "**id**": "30",
                "**code**": "30",
                "**name**": "30",
                "**rank**": "915",
                "**department**": "Clothing"
            }
        }, {
            "**id**": "497433",
            "**sku**": "JT00497433",
            "**sold_out**": false,
            "**color**": {
                "**id**": "16523",
                "**code**": "rinse blac",
                "**name**": "rinse black",
                "**solid_color_group_id**": "4",
                "**solid_color_group_name**": "Black"
            },
            "**size**": {
                "**id**": "37",
                "**code**": "31",
                "**name**": "31",
                "**rank**": "925",
                "**department**": "Clothing"
            }
        }],
        "**categories**": [{
            "**id**": 2,
            "**name**": "Streetwear",
            "**class_id**": "1"
        }, {
            "**id**": 8,
            "**name**": "Denim + Pants",
            "**class_id**": "2"
        }, {
            "**id**": 34,
            "**name**": "Denim",
            "**class_id**": "3"
        }, {
            "**id**": 83,
            "**name**": "5 Pocket",
            "**class_id**": "4"
        }, {
            "**id**": 119,
            "**name**": "Slim",
            "**class_id**": "5"
        }],
        "**original_price**": "90.00",
        "**clean_price**": "90",
        "**original_retail**": "90.00",
        "**clean_retail**": "90"
    },
    "**sale**": {
        "**id**": 10753,
        "**name**": "Premium Denim",
        "**start_date**": "2013-06-19 12:00:00",
        "**end_date**": "2014-03-26 12:00:00"
    },
    "**swatches**": {
        "**126101**": {
            "**sale_id**": 10753,
            "**color_name**": "dry black",
            "**solid_color_name**": "Black",
            "**hex_color**": "#000000",
            "**image**": "http:\/\/ak-images.jackthreads.com\/v1\/image\/953401",
            "**total_quantity**": 6
        }
    }
}