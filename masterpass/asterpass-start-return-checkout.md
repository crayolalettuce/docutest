After user clicks 'buy with MasterPass', auth with MasterPass 

HTTP method: POST /services/v1/masterpass/start_return_checkout

User authorization: required
TLS: required

Required parameters
 callback_url - string Callback url to front-end, used by MasterPass to post data (this url needs to be accessible by MasterPass, and store the tokens passed in that call)


Response
 return_checkout - object 

         callbackUrl - string 
         requestToken - string 
         precheckoutTransactionId - string 
         walletName - string 
         consumerWalletId - string 
         merchantCheckoutId - string 

         version - string 



Example request
        curl -k -d '`oauth_token=38927e9f43939d88399265f0ecade99e&callback_url=https%3A%2F%2Fjackthreads.dev%3A7443%2Fmasterpass%2Ftest_masterpass_callback``' https://stage-jitr-01.jackthreads.com``/services/v1/masterpass/get_redirect_url`

Example response
        { "success": true, "errors": [], "return_checkout": { "requestToken": "8e66fb7fd606028410e85cd0358fb1adea7be6f2", "callbackUrl": "https:\/\/jackthreads.dev:7443\/masterpass\/test_masterpass_callback", "precheckoutTransactionId": "a4a6x55-3ttsu2-i12lss0p-1-i19nioum-7c07", "walletName": "Mobile", "merchantCheckoutId": "a4a6x1ywxlkxzhensyvad1hepuouaesuv", "consumerWalletId": "679", "version": "v6" } }