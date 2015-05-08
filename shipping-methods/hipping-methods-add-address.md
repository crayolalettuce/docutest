Add a new shipping address.

HTTP method: POST /services/v1/shipping
Client authorization: no
User authorization: required
TLS: required

Required parameters
 name  - string Shipping address name
 first_name - string First name
 last_name - string Last name
 address - string Address line 1
 city  - string City
 state  - string State or province
 zip  - string Postal code
 country - string Country
 phone  - string Phone number
 validate - boolean Use Satori to validate the address provided

Optional parameters
 company - string Company name
 address2 - string Address line 2
 is_primary - boolean If true, make this the primary shipping address

Response
 address - object Address info
  id  - integer Shipping address ID
  name  - string Shipping address name
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
  is_primary - boolean True if this is the primary shipping address

Example request
        curl -k -d 'name=api4&first_name=Jacinto&last_name=Shy&address=2121&city=New%20York&state=NY&zip=10012&country=US&phone=1234567890&oauth_token=fb18fc25e7e41608dadddcf567e9fe22&validate=1' https://16.camp.jackthreads.com:9116/services/v1/shipping

Example response
        {`
``  ``"success"``:``true``,``
``  ``"address"``:``{``
``     ``"id"``:``120182``,``
``     ``"name"``:``"api4"``,``
``     ``"first_name"``:``"Jacinto"``,``
``     ``"last_name"``:``"Shy"``,``
``     ``"company"``:``null``,``
``     ``"address"``:``"2121"``,``
``     ``"address2"``:``null``,``
``     ``"city"``:``"New York"``,``
``     ``"state"``:``"NY"``,``
``     ``"zip"``:``"10012"``,``
``     ``"country"``:``"US"``,``
``     ``"phone"``:``"1234567890"``,``
``     ``"is_primary"``:``false``
``  ``}``
``}`