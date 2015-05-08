**This endpoint is deprecated. Please use [Make Primary Payment Method](jackthreads-v1-api-payment-methods-make-primary) instead.**    
 
**Make the given credit card the user’s primary credit card.
 
 HTTP method: POST /services/v1/credit_cards/<id>/make_primary
 Client authorization: no
 User authorization: required
 TLS: required
 
 Required parameters
  id - integer Credit card ID
 
 Response
  credit_card - object Credit card info
   id  - integer Credit card ID
   first_name - string First name
   last_name - string Last name
   company - string Company name
   address - string Address line 1
   address2 - string Address line 2
   city  - string City
   state  - string State or province
   zip  - string Postal code
   country - string Country
   phone  - string Phone number
   last_four - string Last four digits
   exp_month - string Expiration month
   exp_year - string Expiration year
   is_primary - boolean True if this is the primary credit card
   type  - object Credit card type info
    id  - string Type ID
    name  - string Type name
 
 Example request
 `curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://16.camp.jackthreads.com:9116/services/v1/credit_cards/162000/make_primary`
 
 Example response
 `{
   "success":true,
   "credit_card":{
      "id":162000,
      "exp_month":"3",
      "exp_year":"2017",
      "last_four":"1111",
      "first_name":"Jacinto",
      "last_name":"Shy",
      "company":"",
      "address":"1990 Lexington Ave",
      "address2":"Apt 22J",
      "city":"New York",
      "state":"NY",
      "zip":"10035",
      "country":"US",
      "phone":"6469190750",
      "is_primary":true,
      "type":null
   }
 }`**