**Shorten a URL.

HTTP method: GET /services/v1/thrillist/shorten_url
Client authorization: no
User authorization: no
TLS: no

Required parameters
 long_url  - string Original URL

Response
 short_url  - string Shortened URL

Example request
        curl https://16.camp.jackthreads.com:9116/services/v1/thrillist/shorten_url?long_url=http%3A%2F%2Fwww.slashdot.org

Example response
        {
   "success":true,
   "short_url":"http:\/\/thrl.st\/yYLgO4"
}**

**

**