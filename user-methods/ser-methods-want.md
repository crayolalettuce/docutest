HTTP method: POST /services/v1/users/want
Client authorization: required
User authorization: required
TLS: required

Required parameters
 sale_id   - int The current sale the product belongs to
 product_id  - int The product id


Optional parameters
 save_locally   - bool Save the wanted product locally and don't perform the FB OG action

      

**Response**

 success                - boolean


Example request
        curl -skd '`oauth_token=4624a66bf39ec16100b950162474869b&sale_id=8251&product_id=26306``' 'https://jackthreads.dev:7443/services/v1/users/want'`

Example response

{ "success":true
}