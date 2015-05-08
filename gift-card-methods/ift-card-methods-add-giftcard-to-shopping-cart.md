Add a gift card.to the shopping cart

HTTP method: POST /services/v1/gift_cards/add
Client authorization: no
User authorization: required
TLS: required

Required parameters
 name - string 
 from - string 
 amount - integer 
 message  - string 
 email - string 
 email_confirm - string 
 send_later - string 
 send_date (optional) - string 


**Response Example:**

{ "success": true, "errors": [ ], "vals": { "name": "ApiTest", "from": "jt.api.test2.0@gmail.com", "amount": "50.00", "message": "", "email": "jt.api.test2.0@gmail.com", "email_confirm": "jt.api.test2.0@gmail.com", "email_later": 0, "email_date": "", "send_date": "", "send_later": 0, "cc_me": 0 } }