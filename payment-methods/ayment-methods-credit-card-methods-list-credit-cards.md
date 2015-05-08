**This endpoint is deprecated. Please use [List Payment Methods](jackthreads-v1-api-payment-methods-list-payment-methods) instead.**    
 
 
Get a list of the user’s stored credit cards.
 
 HTTP method: GET /services/v1/credit_cards
 Client authorization: no
 User authorization: required
 TLS: required
 
 Response
  credit_cards - array List of the user’s stored credit cards
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
 `curl -k https://16.camp.jackthreads.com:9116/services/v1/credit_cards?oauth_token=fb18fc25e7e41608dadddcf567e9fe22`
 
 Example response
 `{``
 ``  ``"success"``:``true``,``
 ``  ``"credit_cards"``:``[``
 ``     ``{``
 ``        ``"id"``:``162000``,``
 ``        ``"exp_month"``:``"3"``,``
 ``        ``"exp_year"``:``"2017"``,``
 ``        ``"last_four"``:``"1111"``,``
 ``        ``"first_name"``:``"Jacinto"``,``
 ``        ``"last_name"``:``"Shy"``,``
 ``        ``"company"``:``""``,``
 ``        ``"address"``:``"1990 Lexington Ave"``,``
 ``        ``"address2"``:``"Apt 22J"``,``
 ``        ``"city"``:``"New York"``,``
 ``        ``"state"``:``"NY"``,``
 ``        ``"zip"``:``"10035"``,``
 ``        ``"country"``:``"US"``,``
 ``        ``"phone"``:``"6469190750"``,``
 ``        ``"is_primary"``:``true``,``
 ``        ``"type"``:``null``
 ``     ``}``
 ``  ``]``
 ``}`