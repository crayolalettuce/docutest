Tracking the first page being open by mobile apps.

HTTP method: POST /services/v1/eventTracking
Client authorization: yes
User authorization: no
TLS: yes


**Optional parameters**

  DeviceID - string Id of the device

  model - string model of the device
  appID - string app id
  event - string id of the event
  os-version - string version of the mobile operation system
  user_id - int user id



**Example request**

        curl -k -d 'oauth_token=faee8bc28cff7d4d6ca24c87990c438e&DeviceID=1&model=HTC Sensation&event=SUPERSALE&os-version=2.3' https://16.camp.jackthreads.com:9116/services/v1/eventTracking

Example response
        
{
   "success":true
}