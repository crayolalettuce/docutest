**Provides product listing to Google Feeds**


HTTP method: GET /services/v1/google/
Client authorization: no
User authorization: no


Required parameters
 
none


Optional parameters
 page - integer page#
 country code - string country code


Example request


        // provide a full US-based listing of google feed in XML
        curl /services/v1/`feeds/products/google/`
        

        // provide a full US-based listing of google feed in XML with pagination. 5000 items per page.
        curl /services/v1/`feeds/products/google/1`
        

        // Japan-based google feed in XML
        curl /services/v1/`feeds/products/google/JP/`
        

        // 3rd page of the Australia-based Google XML feed.
        curl /services/v1/`feeds/products/google/AU/3`