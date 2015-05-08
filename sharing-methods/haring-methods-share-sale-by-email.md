Share a product by email

HTTP method: POST /services/v1/sales/<sale_id>/share
Client authorization: no
User authorization: yes
TLS: yes

Required parameters
 sale_id  - integer Sale ID
 recipients - array List of recipients


**Optional parameters**

  message - string User-provided message

Response
 total_referrals - integer Total number of referrals

  invalid_emails - integer Number of invalid emails


**Example request**

        curl -k -d 'oauth_token=faee8bc28cff7d4d6ca24c87990c438e&message=Sup&recipients%5B%5D=jacinto%2binv0@thrillist.com' https://16.camp.jackthreads.com:9116/services/v1/sales/5032/share

Example response
        
{
   "success":true,
   "total_referrals":1,
   "invalid_emails":0
}