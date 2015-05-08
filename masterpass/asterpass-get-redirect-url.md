After user clicks 'buy with MasterPass', auth with MasterPass and get redirect url

HTTP method: POST /services/v1/masterpass/get_redirect_url

User authorization: required
TLS: required

Required parameters
 callback_url - string Callback url to front-end, used by MasterPass to post data (this url needs to be accessible by MasterPass, and store the tokens passed in that call)


Response
 redirect_url - string Redirect url to MasterPass. Starts MasterPass login

Example request
        curl -k -d '`oauth_token=38927e9f43939d88399265f0ecade99e&callback_url=https%3A%2F%2Fjackthreads.dev%3A7443%2Fmasterpass%2Ftest_masterpass_callback``' https://stage-jitr-01.jackthreads.com``/services/v1/masterpass/get_redirect_url`

Example response
        {`
``  ``"success"``:``true``,``
``  ``"errors"``:[]``,`
          `"redirect_url"``:``"https:\/\/sandbox.masterpass.com\/Checkout\/Authorize?acceptable_cards=master,amex,discover,visa&checkout_identifier=a4a6x1ywxlkxzhensyvad1hepuouaesuv&oauth_token=2250d2ef87ac17d8dd93007cf199dd9fbeb2ad94&version=v5&suppress_shipping_address=true&shipping_location_profile=US,CA,FR,MEX,NA,UK,USMO,USVA,AUSWALES"`
        }