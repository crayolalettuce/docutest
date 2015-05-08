Verifies that a user is allowed to access display schedule api endpoints based on their oauth token


**HTTP method**: POST /services/v1/display_schedules/authorize

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**Sample Request:**

curl -d "oauth_token=whatever" "https://dev.jitr.jackthreads.com/services/v1/display_schedules/authorize" 


**Sample Response:**


        {
            "success": true,
            "currency": {
                "code": "USD",
                "symbol": "$",
                "name": "US Dollar",
                "locale": "US"
            }
        }
        

**Sample Error Response:**

        
{
    "success": false,
    "errors": {
        "code": "not_authorized"
    },
    "currency": {
        "code": "USD",
        "symbol": "$",
        "name": "US Dollar",
        "locale": "US"
    }
}