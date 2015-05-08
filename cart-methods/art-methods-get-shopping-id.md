Get a shopping id that will be used with Client authorization for the add, remove, set cart methods.


HTTP method: POST /services/v1/cart/shopping_id
Client Authorization: required
User Authorization: no
TLS: required


**Response:**

shopping_id - string Id that will be used to associate with a shopping cart


**Example Request:**

        curl -d 'oauth_token=8f2cae7a24d0a90918a22032f867a089' 'https://jackthreads.dev:7443/services/v1/cart/shopping_id'


**Example Response:**

        {
            "success": true,

            "shopping_id": "9682c3d437505e4b0acc3c7188758bd5"
        }