List the user’s favorite categories.

HTTP method: GET /services/v1/users/categories
Client authorization: no
User authorization: required
TLS: yes

Response
 categories  - array List of favorited categories
  id   - string Category ID
  name   - string Category

Example request
        
curl -k 'https://16.camp.jackthreads.com:9116/services/v1/users/categories?oauth_token=769a6855a375739b2b79a6b85d6d3b46'{"success":true,"categories":[{"id":1,"name":"Contemporary"}]}
Example response
        
{
   "success":true,
   "categories":[
      {
         "id":1,
         "name":"Contemporary"
      }
   ]
}