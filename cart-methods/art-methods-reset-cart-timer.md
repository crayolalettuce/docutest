Extend the cart's timer for checkout. 



HTTP method: POST /services/v1/cart/reset_timer
Client Authorization: no
User Authorization: required
TLS: required


**Optional Query Parameters:**

shopping_id - string ID used to identify a shopping cart
minutes - int Amount to extend the cart timer by, default is the systems cart lifetime (15 min)
**

**

**Response:**

(see [Items in Cart](jackthreads-v1-api-cart-methods-items-in-cart) response format)
**

**

**Example Request:**

        curl 'https://jackthreads.dev:8443/services/v1/cart/reset_timer?oauth_token=882f8a7b55d224272471338670a3f31e'
**

**

**Example Response:**


*{*
*  "success":true,*
*  "cart":{*
*    "qty":1,*
*    "expired":0,*
*    "subtotal":"24.00",*
*    "tax":"0.00",*
*    "shipping":"0.00",*
*    "discount":"0.00",*
*    "store_credit":"0.00",*
*    "gift_card":"0.00",*
*    "coupon_discount":"6.00",*
*    "coupons":[*
*      {*
*        "id":1,*
*        "name":"employee",*
*        "type":"percent",*
*        "method":"auto",*
*        "amount":"6.00",*
*        "desc":"Employee Discount",*
*        "show":true*
*      }*
*    ],*
*    "total":"18.00",*
*    "retail":"24.00",*
*    "saved":"0.00",*
*    "items":[*
*      {*
*        "id":545834,*
*        "sku":"JT00545834",*
*        "cart_id":50000024,*
*        "product_id":155741,*
*        "name":"Five Panel Hat",*
*        "expires":"2014-04-17 13:14:43",*
*        "price":"24.00",*
*        "image":"http:\/\/ak-images.jackthreads.com\/v1\/image\/1199655",*
*        "url":"\/woolf\/hats\/baseball\/five-panel-hat\/products\/155741",*
*        "brand":{*
*          "id":1775,*
*          "name":"Woolf"*
*        },*
*        "color":{*
*          "id":4144,*
*          "name":"Indigo Chambray"*
*        },*
*        "size":{*
*          "id":140,*
*          "name":"One Size"*
*        },*
*        "sale":{*
*          "id":10777,*
*          "name":"The Woolf Collection ",*
*          "start_date":"2013-06-20 12:00:00",*
*          "end_date":"2014-05-01 12:00:00"*
*        },*
*        "qty":1,*
*        "is_expired":false,*
*        "is_returnable":true,*
*        "is_virtual":false,*
*        "est_delivery":"Tue 4\/22\/14 to Mon 4\/28\/14",*
*        "shop_id":"1"*
*      }*
*    ],*
*    "estimated_delivery":"Tue 4\/22\/14 to Mon 4\/28\/14",*
*    "cart_expiration":"2014-04-17 13:14:43",*
*    "instock":true,*
*    "customs":"0.00",*
*    "formatted_summary":[*
*      {*
*        "label":"Subtotal",*
*        "value":"$24.00",*
*        "neg":false*
*      },*
*      {*
*        "label":"Employee Discount",*
*        "value":"$6.00",*
*        "neg":true*
*      },*
*      {*
*        "label":"Total",*
*        "value":"$18.00",*
*        "neg":false*
*      }*
*    ],*
*    "formattedText":"Subtotal: $24.00\nEmployee Discount: $6.00\nTotal: $18.00",*
*    "time_now":1397753984*
*  }*
*}*