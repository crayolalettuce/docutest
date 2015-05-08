Send email invites.

HTTP method: POST /services/v1/invites/send
Client authorization: no
User authorization: required
TLS: required

Required parameters
 recipients - array List of email addresses

Optional parameters
 personal_message - string Personal message
 skip_email - bool If true, invite emails are not sent

Response
 referrals  - integer Total number of successful referrals

Example request
        curl -k -d 'oauth_token=fb18fc25e7e41608dadddcf567e9fe22q&recipients[0]=jacinto%2Bfooball%40thrillist.com' https://16.camp.jackthreads.com:9116/services/v1/invites/send

Example response
        {`
``  ``"success"``:``true``,``
``  ``"referrals"``:``1``
``}`