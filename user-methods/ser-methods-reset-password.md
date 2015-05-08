Reset the user’s password.

HTTP method: POST /services/v1/users/password_reset
Client authorization: required
User authorization: no
TLS: yes

Response
 message - string Success message

Example request
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22&email=jacinto%2Bcu11%40thrillist.com' https://16.camp.jackthreads.com:9116/services/v1/users/password_reset

Example response
        {`
``   ``"success"``:``true``,``
``   ``"message"``:``"An e-mail with your new password has been sent to jacinto@thrillist.com"``
``}`