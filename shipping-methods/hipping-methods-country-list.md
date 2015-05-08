Retrieves a list of supported countries.


HTTP Method: GET /services/v1/countries
Client authorization: No
User authorization: No
TLS:  No


**Required parameters:**


        group - `string`  Group of countries to return.  As countries are rolled out they are not automatically included in the API response until the client app can confirm it can handle the countries without breaking.  The group that is passed will return all countries in that group and in all groups that pre-date it.  If this parameter is not passed the API will use the group below marked as default.
Groups:

* 20080731: US
* 20081010: CA
* 20130327 [default]: AU, UK
* 20130910: FR, CH, SG, RU, NZ, MX, KR, DE, IT, HK, JP

*
*

**Response**:
        success - bool  True if the call succeeded`countries - array`  List of countries; contains the following keys:

        name - string  Country name
        code - string  Country code (two characters)
        state - array  List of states within this country, if applicable.`code - string`  State code (no character max)
        name - string  State name


**Example Request/Response**

        

        curl -s http://api.jackthreads.com/services/v1/countries?group=20130910






        {
           "countries":[
              {
                 "name":"Australia",
                 "code":"AU",
                 "state":[
                    {
                       "code":"ACT",
                       "name":"Australian Capital Territory"
                    },
                   [...]
                 ]
              },
              {
                 "name":"Canada",
                 "code":"CA",
                 "state":[
                    {
                       "code":"AB",
                       "name":"Alberta"
                    },
                    [...]
                 ]
              },
              {
                 "name":"France",
                 "code":"FR",
                 "state":[
        

                 ]
              },
              {
                 "name":"Germany",
                 "code":"DE",
                 "state":[
        

                 ]
              },
              {
                 "name":"Hong Kong",
                 "code":"HK",
                 "state":[
        

                 ]
              },
              {
                 "name":"Italy",
                 "code":"IT",
                 "state":[
        

                 ]
              },
              {
                 "name":"Japan",
                 "code":"JP",
                 "state":[
        

                 ]
              },
              {
                 "name":"Mexico",
                 "code":"MX",
                 "state":[
        

                 ]
              },
              {
                 "name":"New Zealand",
                 "code":"NZ",
                 "state":[
        

                 ]
              },
              {
                 "name":"Russia",
                 "code":"RU",
                 "state":[
        

                 ]
              },
              {
                 "name":"Singapore",
                 "code":"SG",
                 "state":[
        

                 ]
              },
              {
                 "name":"South Korea",
                 "code":"KR",
                 "state":[
        

                 ]
              },
              {
                 "name":"Switzerland",
                 "code":"CH",
                 "state":[
        

                 ]
              },
              {
                 "name":"United Kingdom",
                 "code":"UK",
                 "state":[
        

                 ]
              },
              {
                 "name":"United States",
                 "code":"US",
                 "state":[
                    {
                       "code":"AL",
                       "name":"Alabama"
                    },
                    [...]
                 ]
              }
           ],
           "success":true
        }