Get a list of brands for the given category.

HTTP method: GET /services/v1/categories/<id>/brands
Client authorization: no
User authorization: no
TLS: no

Required parameters
 id - integer Category ID

Response
 brands  - array List of brands
  id  - integer Brand ID
  name  - string Brand name
  bio  - string Biography

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/categories/2/brands

Example response
        {`
``   ``"success"``:``true``,``
``   ``"brands"``:``[``
``      ``{``
``         ``"id"``:``168``,``
``         ``"name"``:``"Penguin Footwear"``,``
``         ``"bio"``:``"In 1955, Munsingwear introduced the first iconic golf shirt, giving way to a new sportswear lifestyle. The ORIGINAL PENGUIN logo was popular through the 1970s and was worn by the likes of Arnold Palmer, Bob Hope, Bing Crosby and Richard Nixon, among others.\r\nIn keeping with the suburban golf and social club sensibility of the original brand, an ORIGINAL PENGUIN"``
``      ``}``,``
``      ``{``
``         ``"id"``:``540``,``
``         ``"name"``:``"JD FISK"``,``
``         ``"bio"``:``"J.D. FISK IS THE NEWEST VENTURE INTO MEN\u2019S FOOTWEAR FROM ESTABLISHED WOMEN\u2019S BRAND DOLCE VITA. THE INSPIRATION FOR THE BRAND SPANS FROM TRADITIONAL LOOKS WITH CLASSIC STYLING TO EDGIER APPROACHES THAT NOD TO THE UK PUNKS OF THE 70\u2019S AND 80\u2019S. THE MISSION OF THE BRAND, LIKE DOLCE VITA, IS TO PROVIDE HIGH-END QUALITY AT PRICES THAT ARE WITHIN REACH"``
``      ``}``,``
``      ``{``
``         ``"id"``:``538``,``
``         ``"name"``:``"Impulse Footwear"``,``
``         ``"bio"``:``null``
``      ``}``,``
``      ``{``
``         ``"id"``:``461``,``
``         ``"name"``:``"PF Flyers"``,``
``         ``"bio"``:``""``
``      ``}``
``   ``]``
``}`