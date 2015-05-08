List brands.

HTTP method: GET /services/v1/brands
Client authorization: no
User authorization: no
TLS: no

Optional parameters
 current  - boolean If true, get a list of the brands represented in current sales

Response
 brands  - array List of brands
  id  - integer Brand ID
  name  - string Brand name
  bio  - string Brand biography

Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/brands?current=1

Example response
        {`
``  ``"success"``:``true``,``
``  ``"brands"``:``[``
``     ``{``
``        ``"id"``:``411``,``
``        ``"name"``:``"Second Sunday"``,``
``        ``"bio"``:``"Founded in 2010, Second Sunday is our realization of a simple life well lived. Representing a work of heart amongst a group of friends and designers, the brand is an innovative approach to functional design and honest craftsmanship. The brand's caring emphasis on gentle fabrics and superior fit is a unifying theme in all of its garments, which are made to be worn often and keep shape with age.\r\n \r\nRehab by Second Sunday represents the other half of our brand and lifestyles. Rehab focuses on creating casual-wear that consistently delivers comfort and relaxation without sacrificing garment quality or aesthetic appeal. And through this, Rehab by Second Sunday completes our vision of a "``
``     ``}``,``
``     ``{``
``        ``"id"``:``160``,``
``        ``"name"``:``"Shut Skateboards"``,``
``        ``"bio"``:``"Shut Skates from NYC - To know it is to love it. To not know it leads one to learn about it. This iconic company was home grown by a group of hungry teens in 1986 with the desire to provide for their need of functional skateboards. The perception of how one starts a skateboard company was changed forever when Shut first made its mark on the world and took the industry by storm. Armed with above standard decks and skating talent that puts top pros on the edge of their seats, Shut is back to deliver even more flavor and style to the ever-evolving skateboard market. Shut skateboards are proudly made in the U.S.A. shutnyc.com\r\nSHUT Skateboards are proudly Made in the USA from the highest quality materials available, and come in an array of shapes and sizes for all styles\r\nof riding."``
``     ``}``
``  ``]``
``}`