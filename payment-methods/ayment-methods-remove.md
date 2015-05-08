Remove the given payment method from the user’s account.

HTTP method: POST /services/v1/payment_methods/remove
Client authorization: no
User authorization: required
TLS: required

Required parameters
 type - string Payment Method Type (c/p/f)

 id - integer ID of payment method

Response
 success - boolean True if the payment method was removed, false on error

Example request
        curl -k -d 'type=c&id=123456&oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://rc.jackthreads.com/services/v1/payment_methods/remove

Example response
        {
  "success":true
}