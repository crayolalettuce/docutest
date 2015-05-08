HTTP method: GET /services/v1/users/want
Client authorization: required
User authorization: required
TLS: required

Required parameters

Optional parameters
      

**Response**

 products      - array List of wanted product ids


Example request
        curl -sk '`https://jackthreads.dev:7443/services/v1/users/want?oauth_token=4624a66bf39ec16100b950162474869b`'
Example response

{ "success":true, "products":[
    '12345',

    '67890'

 ] }