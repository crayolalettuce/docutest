Removes all entities attached to a schedule and associates the newly passed entities


**HTTP method**: POST /services/v1/display_entities/:display_entity_id/exclusions

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**URL Parameters**:
    :display_entity_id - id of the display entity to create exclusions for

**Required Parameters**:
    display_exclusions - array - array of JSON objects consisting of display exclusion information

**Display_exclusions Parameters**:
    type - string - the class of the exclusion, such as "RequestSource" or "Country"
    code - string - the name of the exclusion, such as "android" or "au"


**Sample Request:**

curl -d 'display_exclusions=[{"type":"RequestSource", "code":"android"}]' "https://dev.jitr.jackthreads.com/services/v1/display_entities/11451/exclusions" 


**Sample Response:**


        {
            "success": true,
            "data": [
                {
                    "exclusion_class": "Sale",
                    "exclusion_class_id": "14277",
                    "exclusion_type": "RequestSource",
                    "exclusion_type_id": "1"
                }
            ],
            "errors": [],
            "currency": {
                "code": "USD",
                "symbol": "$",
                "name": "US Dollar",
                "locale": "US"
            }
        }