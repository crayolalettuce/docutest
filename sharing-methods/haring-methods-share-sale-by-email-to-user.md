Share a sale by email

HTTP method: POST /services/v1/sales/<sale_id>/share/user
Client authorization: yes
User authorization: no
TLS: yes

Required parameters
 sale_id - integer Sale ID
 username - string Username
 recipients - array List of recipients


**Optional parameters**

  message - string User-provided message
  query_string - string Will be appended to the URL

Response
 total_referrals - integer Total number of referrals

  invalid_emails - integer Number of invalid emails


**Example request**

        curl -k -d 'oauth_token=`bf4ee104ac3529ec3950b9a2a044bbea``&message=Hello%20World&recipients%5B%5D=kkhawaja_api1@thrillist.com&`username=kkhawaja_api' https://16.camp.jackthreads.com:9116/services/v1/sales/5032/share/user

Example response
        
{
   "success":true,
   "total_referrals":1,
   "invalid_emails":0
}