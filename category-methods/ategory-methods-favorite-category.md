Favorite or unfavorite a category.

HTTP method: POST /services/v1/categories/<id>/favorite
Client authorization: no
User authorization: required
TLS: yes

Required parameters
 id   - integer Category ID

Optional parameters
 remove  - boolean If true, remove from favorite categories

Response
 categories  - array List of favorited categories
  id   - string Category ID
  name   - string Category

Example request
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://16.camp.jackthreads.com:9116/services/v1/categories/3/favorite

Example response
        {`
``   ``"success"``:``true``,``
``   ``"categories"``:``[``
``      ``{``
``         ``"id"``:``3``,``
``         ``"name"``:``"Skate, Surf, Snow"``
``      ``}``
``   ``]``
``}`