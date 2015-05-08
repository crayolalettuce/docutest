**This endpoint is deprecated. Please use [Remove Payment Method](jackthreads-v1-api-payment-methods-remove) instead.**    
 
Remove the given credit card from the user’s account.
 
 HTTP method: POST /services/v1/credit_cards/<id>/remove
 Client authorization: no
 User authorization: required
 TLS: required
 
 Required parameters
  id  - integer Credit card ID
 
 Example request
 `curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://16.camp.jackthreads.com:9116/services/v1/credit_cards/162004/remove`
 
 Example response
 `{``
 ``"success"``:``true``
 ``}`