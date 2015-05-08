Complete purchase. Items should be in cart and shipping address should already be saved.



HTTP Method: POST /services/v1/checkout
Client authorization: No
User authorization: Yes
TLS: required


**Required parameters:**


        shipping_address - `int`  Shipping address ID
        shipping_method - `string`  Selected shipping mode
*
*

**Required parameters when payment method is already stored:**


        payment_method_type - char  Type of payment used for purchase
        payment_method_id - int  Type of payment used for purchase

**

**

**Required parameters when adding a new payment method (currently only available for Google Wallet):**


        add_payment_type - char  Type of payment to add.  Currently the only valid value is "g".
        add_payment_full_name - string  Customer's full name from their billing info`add_payment_address - string`  Billing address
        add_payment_city - string  Billing city
        add_payment_state - string  Billing state
        add_payment_zip - string  Billing ZIP/postal code
        add_payment_country - string  Billing country
        add_payment_phone - string  Billing phone number
        add_payment_card_number - int  Credit card number
        add_payment_cvv - int  Card security code
        add_payment_exp_month - string  Card expiration month
        add_payment_exp_year - string  Card expiration year
        add_payment_email - string  Associated email address
        add_payment_description - string  Payment method description from provider (e.g. Visa 1111 via Google Wallet)
        add_payment_object_id - string  Object ID from provider**

**

**Optional parameters:**


        source - string  Origin of purchase, for analytics; generally the device type or OS (e.g. iphone, ipad, android, etc)
        shop_id - int  ID of commerce shop placing the order

**Response**:
        success - bool  True if checkout succeeded and resulted in an order, otherwise False.
        order_id - int  Order ID if checkout success


**Example Request (payment method already stored):**

``curl -ks 'https://rc.jackthreads.com/services/v1/checkout?oauth_token=6dd20496299f37eb909cd98ed1fde0e5&payment_method_type=c&payment_method_id=162000&shipping_method=USPR&shipping_address=118242'``


**Example Response**




        {
          "success": true,
          "order_id": 123456
}



**

**

**Example Request (adding and paying with a Google Wallet account):**

``curl -ks 'https://rc.jackthreads.com/services/v1/checkout?oauth_token=6dd20496299f37eb909cd98ed1fde0e5&shipping_address=54321&shipping_method=UGND&add_payment_type=g&add_payment_full_name=John%20Doe&add_payment_address=568%20Broadway&add_payment_city=New%20York&add_payment_state=NY&add_payment_zip=10012&add_payment_country=US&add_payment_phone=1234567890&add_payment_card_number=4111111111111111&add_payment_cvv=098&add_payment_exp_month=11&add_payment_exp_year=2022&add_payment_email=jdoe%40thrillist.com&add_payment_description=Visa%201111%20via%20Google%20Wallet&add_payment_object_id=1234abcdef'``
        

        **Example Response**

Same as above