# Revoke token access

**HTTP method**: POST /services/v1/oauth/token/invalidate

|**Client authorization**|No|
|**User authorization**|No|
|**TLS**|Yes|


**Required Parameters**:
* client_id
* client_secret
* oauth_token



**Sample Request:**

`curl -d "client_id=jackthreads&client_secret=kobol&oauth_token=46d68abfa0dff72b493b5be573f4fbc5" "https://jitr.jackthreads.dev/services/v1/oauth/token/invalidate"`


**Sample Response:**
`
{
	 "success":true
}
`