Add a new payment method.



HTTP Method: POST /services/v1/payments/add
Client authorization: No
User authorization: Yes
TLS: required


**Note**:

* Fields labeled "obj|strings" can be posted in two different ways.  The fields under these parameters can be passed as part of an object (e.g. billing[address]) or they can be passed individually, the field names prefixed by the parameter name (e.g. billing_address).



**Required parameters:**


        vendor - `char`  Payment method source.  Supported values:a - Apple Pay
        payment - obj|strings  Payment data: 
        nonce - string  Payment nonce
        is_primary - bool  (Optional) True if the payment method should be the primary method
        billing - obj|strings  Billing address:
        name - string  Full billing name, first and last.  If individual first and last names are available, post them separately and do not use this field.
        first_name - string  First name
        last_name - string  Last name`address - string`  Address
        address2 - string  (Optional) Address 2
        company - string  (Optional) Company name.  Can be used for address3/least significant address data
        city - string  City
        state - string  2-char state/province code
        zip - string  ZIP or postal code
        country - string  2-char country code
        phone - string  (Optional) Phone number
        

``**Optional parameters:**`
``shipping - obj|strings`  (Optional) New shipping address.  If a matching address exists then a new address will not be added.`name - string`  Full name, first and last.  If individual first and last names are available, post them separately and do not use this field.
        first_name - string  First name

        last_name - string  Last name`address - string`  Address
        address2 - string  (Optional) Address 2
        company - string  (Optional) Company name.  Can be used for address3/least significant address data
        city - string  City
        state - string  2-char state/province code`zip - string`  ZIP or postal code`country - string`  2-char country code`phone - string`  (Optional) Phone number



**Response**:
        success - bool  True if the API did not experience any general processing errors
        payment - object  Payment results
        success - bool  True if the payment method was added successfully
        payment_method_type - string  (on success=true) Type of the added payment method.  It is not expected for this to differ from the posted vendor param.
        payment_method_id - int  (on success=true) ID of the new payment method
        error - string  (on success=false) Error message if there was a problem adding the payment method.  This can be displayed to the user
        error_code - string  (on success=false) Error code representing the technical reason for failure
        shipping - object  Shipping address results

        success - bool  True if no shipping address was provided or if the provided address was added successfully
        address_id - int  ID of the new address.  Null if no address was provided and thus not added.
        errors - array  (on success=false) Error messages if there was a problem adding the shipping address.  These can be displayed to the user
        error_code - string  (on success=false) Error code representing the technical reason for failure


**Example Full Request (address, payment method and shipping_method provided)**

        curl -ksd 'oauth_token=6dd20496299f37eb909cd98ed1fde0e5&vendor=a&payment_nonce=1a2b3c4d5e6ff6e5d4c3b2a1&billing_name=Johnathan%20Doe&billing_address=568%20Broadway&shipping_name=John%20Doe' 'https://rc.jackthreads.com/services/v1/payments/add'


**Example Response**




        {
          "success": true,
          "payment": {
            "success": true,
            "payment_method_type": "a",
            "payment_method_id": 1598432
          },
          "shipping": {
            "success": true,
            "address_id": 95642842
          }
        }