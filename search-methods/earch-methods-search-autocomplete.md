Get a list of suggested search terms



HTTP method: POST /services/v1/search/autocomplete
Client authorization: No
User authorization: No
TLS: No



Required Parameters:
    q - string Search string


Response: *(Where q="sweat")*
{
 "success":true, "terms":[ "sweatshirts", "sweaters", "sweats" ] }