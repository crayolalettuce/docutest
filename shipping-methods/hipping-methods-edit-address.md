Edit the given shipping address.

HTTP method: POST /services/v1/shipping/<id>/edit
Client authorization: no
User authorization: required
TLS: required

Required parameters
 id - integer Shipping address ID

Optional parameters
 name  - string Shipping address name
 first_name - string First name
 last_name - string Last name
 address - string Address line 1
 city  - string City
 state  - string State or province
 zip  - string Postal code
 country - string Country
 phone  - string Phone number
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
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22q&company=Thrillist' https://16.camp.jackthreads.com:9116/services/v1/shipping/118243/edit

Example response
        {`
``  ``"success"``:``true``,``
``  ``"address"``:``{``
``     ``"id"``:``118242``,``
``     ``"name"``:``"Work"``,``
``     ``"first_name"``:``"Jacinto"``,``
``     ``"last_name"``:``"Shy"``,``
``     ``"company"``:``"Thrillist"``,``
``     ``"address"``:``"568 Broadway"``,``
``     ``"address2"``:``"Suite 607"``,``
``     ``"city"``:``"New York"``,``
``     ``"state"``:``"NY"``,``
``     ``"zip"``:``"10012"``,``
``     ``"country"``:``"US"``,``
``     ``"phone"``:``"6469190750"``,``
``     ``"is_primary"``:``true``
``  ``}``
``}`