Add credit card to the user’s account.

HTTP method: POST /services/v1/credit_cards
Client authorization: no
User authorization: required
TLS: required

Required parameters
 first_name - string First name
 last_name - string Last name
 address - string Address line 1 (GIP only)
 city  - string City (GIP only)
 state  - string State or province (GIP only)
 zip  - string Postal code
 country - string Country
 phone  - string Phone number  (GIP only)
 card_number - string Credit card number
 cvv  - string Security code
 exp_month - string Expiration month (MM)
 exp_year - string Expiration year (YYYY)

Optional parameters
 company - string Company name
 address2 - string Address line 2

is_primary - boolean If true, make this the primary credit card
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
        curl -k -d 'card_number=1221211212212&cvv=121&first_name=Jacinto&last_name=Shy&address=568%20Broadway&city=New%20York&state=NY&oauth_token=fb18fc25e7e41608dadddcf567e9fe22&phone=1234567890&country=US&zip=10012&exp_month=12&exp_year=2014' https://16.camp.jackthreads.com:9116/services/v1/credit_cards

Example response
        {`
``  ``"success"``:``true``,``
``  ``"credit_card"``:``{``
``     ``"id"``:``162012``,``
``     ``"exp_month"``:``"12"``,``
``     ``"exp_year"``:``"2014"``,``
``     ``"last_four"``:``"2212"``,``
``     ``"first_name"``:``"Jacinto"``,``
``     ``"last_name"``:``"Shy"``,``
``     ``"company"``:``""``,``
``     ``"address"``:``"568 Broadway"``,``
``     ``"address2"``:``null``,``
``     ``"city"``:``"New York"``,``
``     ``"state"``:``"NY"``,``
``     ``"zip"``:``"10012"``,``
``     ``"country"``:``"US"``,``
``     ``"phone"``:``"1234567890"``,``
``     ``"is_primary"``:``true``,``
``     ``"type"``:``null``
``  ``}``
``}`