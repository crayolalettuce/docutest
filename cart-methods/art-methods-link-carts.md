Link a users logged in cart with cart associated with just the Shopping Id.


HTTP method: POST /services/v1/cart/link_cart
Client Authorization: no
User Authorization: required
TLS: required


**Response:**

oauth_token - string User token
shopping_id - string Id that will be used to associate with a shopping cart


**Example Request:**

        curl -d 'oauth_token=8f2cae7a24d0a90918a22032f867a089&`shopping_id=00fd615be1ef346c3cce7edeec7b521e``' 'https://jackthreads.dev:7443``/services/v1/cart/link_cart``'`


**Example Response:**

        {
            "success": true
        }