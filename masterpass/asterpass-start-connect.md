After user clicks 'buy with MasterPass', auth with MasterPass 

HTTP method: POST /services/v1/masterpass/start_connect

User authorization: required
TLS: required

Required parameters
 callback_url - string Callback url to front-end, used by MasterPass to post data (this url needs to be accessible by MasterPass, and store the tokens passed in that call)


Response
 lightbox_params - object 

         callbackUrl - string 
         requestToken - string 
         pairingRequestToken - string 
         requestedDataTypes - array 
         merchantCheckoutId - string 

         requestedDataTypes - string 

         allowedCardTypes - array 

         suppressShippingAddressEnable - bool 


         requestPairing - bool 


         loyaltyEnabled - bool 


         allowedLoyaltyPrograms - array 


         requestBasicCheckout - bool 


         version - string 


Example request
        curl -k -d '`oauth_token=38927e9f43939d88399265f0ecade99e&callback_url=https%3A%2F%2Fjackthreads.dev%3A7443%2Fmasterpass%2Ftest_masterpass_callback``' https://stage-jitr-01.jackthreads.com``/services/v1/masterpass/get_redirect_url`

Example response
        { "success": true, "errors": [], "lightbox_params": { "callbackUrl": "https:\/\/jackthreads.dev:7443\/masterpass\/test_masterpass_callback", "requestToken": "85430777c853944b3fd93eaf1d9472f49ab8a02a", "pairingRequestToken": "60fcd5556671ca5253ce0b99c791132d74f3d8b0", "requestedDataTypes": ["ADDRESS", "CARD"], "merchantCheckoutId": "a4a6x1ywxlkxzhensyvad1hepuouaesuv", "allowedCardTypes": ["amex", "visa", "master", "discover"], "suppressShippingAddressEnable": false, "requestPairing": true, "loyaltyEnabled": false, "allowedLoyaltyPrograms": [], "requestBasicCheckout": false, "version": "v6" } }