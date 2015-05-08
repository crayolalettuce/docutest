HTTP method: POST /services/v1/users/want
Client authorization: required
User authorization: required
TLS: required

Required parameters
 product_id  - int The product id


Optional parameters
 delete   - bool Set to true to unwant the product.

      

**Response**

 success                - boolean


Example request
        curl -skd '`oauth_token=4624a66bf39ec16100b950162474869b&product_id=26306&delete=1``' 'https://jackthreads.dev:7443/services/v1/users/want'`

Example response

{ "success":true
}