#### **[]()Get a list of sales.
HTTP method: GET /services/v1/sales
Client authorization: no
User authorization: no
TLS: no



Optional parameter
 type   - string Only retrieve sales of the given sale type (default: retrieve all sales)
        codes - array Possible values are "sale" (normal sales), "seasonal" (seasonal sales), "mobile" (mobile sales), "ipad" (iPad-only sales) and "mobile_hidden" (hidden mobile sales)


Response

sales   - array List of sales
id   - integer Sale ID
name   - string Sale name
start_date  - string Start date
end_date          - string End date
type           - string Sale type
image   - string Image URI
brands   - array List of brand info
 id   - integer Brand ID
 name   - string Brand name
sizes   - array List of size info
 id   - integer Size ID
 name   - string Size
sale_element         - object
        id

        title

        body



**Sale type enumeration
 sale  - Regular sale
 seasonal - Seasonal sale
 mobile  - Mobile-exclusive sale**

** ipad     - iPad-exclusive sale**

**

**Example request
        curl http://16.camp.jackthreads.com:9016/services/v1/sales

Example response
        {`
``   ``"success"``:``true``,``
``   ``"sales"``:``[``
``      ``{``
``         ``"id"``:``3595``,``
``         ``"name"``:``"Neff Watches"``,``
``         ``"start_date"``:``"2011-09-11 12:00:00"``,``
``         ``"end_date"``:``"2011-09-14 12:00:00"``,`
``         ``"type"``:``"sale"``,`
``         ``"image"``:``"http:\/\/16.camp.jackthreads.com:9016\/data\/display_entities\/"``,``
``         ``"brands"``:``[``
``            ``{``
``               ``"id"``:``"637"``,``
``               ``"name"``:``"Neff Headwear"``
``            ``}``
``         ``]``,``
``         ``"sizes"``:``[``
``            ``{``
``               ``"id"``:``"140"``,``
``               ``"name"``:``"One Size"``
``            ``}``
``         ``],`
                 "**sale_element**": {

                    "**id**":"1234",

                    "**title**":"Neff Watches",
                    "**body**":"`Elwood tees are all about the Big Picture.`"
                 }
              `}``,``
``      ``{``
``         ``"id"``:``3500``,``
``         ``"name"``:``"Quiksilver Accessories"``,``
``         ``"start_date"``:``"2011-09-11 12:00:00"``,``
``         ``"end_date"``:``"2011-09-14 12:00:00"``,`
``         ``"type"``:``"sale"``,`
``         ``"image"``:``"http:\/\/16.camp.jackthreads.com:9016\/data\/display_entities\/2011\/08\/6jmra4x6z0eha7z.jpg"``,``
``         ``"brands"``:``[``
``            ``{``
``               ``"id"``:``"210"``,``
``               ``"name"``:``"Quiksilver"``
``            ``}``
``         ``]``,``
``         ``"sizes"``:``[``
``            ``{``
``               ``"id"``:``"141"``,``
``               ``"name"``:``"Small"``
``            ``}``,``
``            ``{``
``               ``"id"``:``"125"``,``
``               ``"name"``:``"Medium"``
``            ``}``,``
``            ``{``
``               ``"id"``:``"122"``,``
``               ``"name"``:``"Large"``
``            ``}``,``
``            ``{``
``               ``"id"``:``"148"``,``
``               ``"name"``:``"X Large"``
``            ``}``,``
``            ``{``
``               ``"id"``:``"140"``,``
``               ``"name"``:``"One Size"``
``            ``}``
``         ``],`
                 "**sale_element":{}**`
``      ``}``
``   ``]``
``}`