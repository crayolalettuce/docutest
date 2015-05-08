Retrieves a list of supported countries.


HTTP Method: GET /services/v1/country_format
Client authorization: No
User authorization: No
TLS:  No



**Optional parameters:**

        locale - `string`  Country code of the international locale the user is in
        limit_locale - `bool` Limit the response to only the locale passed
 **Response**:
        success - bool  True if the call succeeded`countries - array`  List of countries; contains the following keys:
        Country - array  Country name

        name - string  Country name

        

        

        code - string  Country code

        Currency - array  Currency this country is using

        name - string  Full currency name

        code - string  Currency code

        symbol - string  Currency symbol

        AddressFormat - array  List of fields that should be shown in the add/edit/create address form

        display_name - string  What the user should see

        jitr_name - string  What the variable should be passed to the API as

        required - string  Whether or not this is a required field

        rank - string  The order in which these fields should appear on the form

        State - array  List of states within this country, if applicable.`code - string`  State code (no character max)
        name - string  State name

**

        **

**

**Example**

**

**`curl -s https://api.jackthreads.com/services/v1/country_format?locale=AU&limit_locale=1`**



{"success": true,"countries": [{"Country": {"id": "13","name": "Australia","code": "AU"},"Currency": {"name": "Australian Dollar","code": "AUD","symbol": "A$ ","id": "2"},"AddressFormat": [{"display_name": "Address","jitr_name": "address","required": true,"rank": "1","country_id": "13"},{"display_name": "Address Line 2","jitr_name": "address2","required": false,"rank": "2","country_id": "13"},{"display_name": "Suburb/Town","jitr_name": "city","required": true,"rank": "3","country_id": "13"},{"display_name": "State","jitr_name": "state","required": true,"rank": "4","country_id": "13"},{"display_name": "Postal Code","jitr_name": "zip","required": true,"rank": "5","country_id": "13"},{"display_name": "Country","jitr_name": "country","required": true,"rank": "6","country_id": "13"}],"State": [{"code": "ACT","name": "Australian Capital Territory","country_id": "13"},{"code": "NSW","name": "New South Wales","country_id": "13"},{"code": "NT","name": "Northern Territory","country_id": "13"},{"code": "QLD","name": "Queensland","country_id": "13"},{"code": "SA","name": "South Australia","country_id": "13"},{"code": "TAS","name": "Tasmania","country_id": "13"},{"code": "VIC","name": "Victoria","country_id": "13"},{"code": "WA","name": "Western Australia","country_id": "13"}]}],"currency": {"code": "AUD","symbol": "A$ ","name": "Australian Dollar","locale": "AU"}}