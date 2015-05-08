Test if a given user is registered on JackThreads.

HTTP method: GET /services/v1/users/is_jt_user
Client authorization: yes
User authorization: no
TLS: yes

Required parameters
One of:

id - integer User ID
email - string User’s email address
Response

is_tl_user - boolean True if the user is registered with Thrillist
Example request
        curl -k https://16.camp.jackthreads.com:9116/services/v1/users/is_jt_user?email=jacinto%40thrillist.com&oauth_token=bf55420723d51253d5d23a665712b4cf

Example response
        {`
``   ``"success"``:``true``,``
``   ``"is_jt_user"``:``true``
``}`