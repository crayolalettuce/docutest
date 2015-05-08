Send auth credentials obtained from MasterPass postback to JITR, allowing JITR to enable MasterPass payment for the user

HTTP method: POST /services/v1/masterpass/set_payment

User authorization: required
TLS: required

Required parameters
 mpstatus - string Status response from previous 'start connect' or 'return checkout' call 
 shop_id - integer (default: 1, jackthreads) 
 mp_checkout_resource_url  - string masterpass checkout resource url received from previous 'start connect' or 'return checkout' call 
 mp_oauth_token - string masterpass oauth token received from previous 'start connect' or 'return checkout' call 
 mp_oauth_verifier  - string masterpass oauth verifier received from previous 'start connect' or 'return checkout' call 


Optional parameters
 mp_pairing_token - string masterpass oauth token received from previous 'start connect' or 'return checkout' call 
 mp_pairing_verifier  - string masterpass oauth verifier received from previous 'start connect' or 'return checkout' call 


Response
 errors - object Credit card verification errors
        shipping_address - integer Address id as in checkout api call
        payment_method_type - string Payment method type for masterpass
        payment_method_id - integer Id of masterpass account


Example request
        curl -k -d '`oauth_token=38927e9f43939d88399265f0ecade99e&mpstatus=success&mp_checkout_resource_url=https%253A%252F%252Fsandbox.api.mastercard.com%252Fonline%252Fv5%252Fcheckout%252F6854073%253Fwallet%253Dphw&mp_oauth_verifier=c3a3e829d658e131297d103132d74255a1631a06&mp_oauth_token=b5ced32c08ba13ffe9d17605f2e3718535920384&shop_id=1`' `https://stage-jitr-01.jackthreads.com/services/v1/masterpass/set_payment`

Example response
        {`
``  ``"success"``:``true``,``
``  ``"errors"``:``{``},`
  "**shipping_address**":1670173,
  "**payment_method_type**":"m",
  "**payment_method_id**":2`
``}`



        {`
``  ``"success"``:``false``,``
``  ``"errors"``:``{`
            "h3":"`Invalid Token`",
    "`code":"invalid_fields",`
            "fields":{

                "card_number":"The Card Number is not long enough and must contain at least 13 digits.",
                "exp_month":"Expiration Month is required",
                "exp_year":"Expiration Year is required",
                "first_name":"First Name is required",
                "last_name":"Last Name is required",
        
        "address":"Address is required",
        "city":"City is required",
        "state":"State is required",
        "country":"Country is required",
        "phone":"Phone Number is required"
            }

         }`
``}`