Get shipment details for a shipment in FAILED billing_status, needed for payment resolution



HTTP method: GET /services/v1/shipment/:id/billing
Client authorization: No
User authorization: Required
TLS: Required


**Required Parameters:**

id - integer Order ID


**Response:**

user_addresses - object List of address belonging to the user
payment_methods - object List of saved payment methods
shipment - object Shipment Info - Contains Shipment, Order, Items



**Example Request:**

        curl -k "https://jackthreads.dev:7443/services/v1/shipment/1670009/billing?oauth_token=ea5d78e5f16a5873689789f99d05b8f7"