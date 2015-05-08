Ping for internal tracking.

HTTP method: POST /services/v1/ping
Client authorization: no
User authorization: yes
TLS: yes


**Optional parameters**

  source - string Platform (default: "api")
  version - string Platform version


**Example request**

        curl -k -d 'oauth_token=faee8bc28cff7d4d6ca24c87990c438e&source=iphone&version=1.2' https://16.camp.jackthreads.com:9116/services/v1/ping

Example response
        
{
   "success":true
}