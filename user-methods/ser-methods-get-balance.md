Get a user’s account balance.

HTTP method: GET /services/v1/users/balance
Client authorization: no
User authorization: required
TLS: yes

Response
 balance - string Account balance

Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/users/balance?oauth_token=fb18fc25e7e41608dadddcf567e9fe22

Example response
        {`
``  ``"success"``:``true``,``
``  ``"balance"``:``"20.00"``
``}`