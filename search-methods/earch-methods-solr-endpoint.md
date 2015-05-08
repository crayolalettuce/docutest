Query any Solr core for specific information using Solr syntax.

**HTTP method:** GET or POST /services/v1/solr (GET requests will be cached at the CDN, POSTs will not)
**Client authorization:** yes
**User authorization:** no
**TLS:** yes

Required parameters
**    **core                 - string Solr core to query (product_indexer, mosaic, metaverse, etc...)**    **searchHandler - string Search handler or node to use on the core (find.json, search.json, dsearch.json, etc...)




Solr Whitelist
**    **For security purposes we have created a whitelist of allowed Solr cores and searchHandlers that can be accessed from this endpoint.     
    This is described in the SolrController class and currently is:**

**

```
    [product_indexer] => Array ( [0] => search.json [1] => dsearch.json [2] => autocomplete.json [3] => suggest.json ) [mosaic] => Array ( [0] => find.json ) [metaverse] => Array ( [0] => find.json ) [hyperion] => Array ( [0] => suggest.json [1] => terms.json [2] => search.json [3] => get.json [4] => instant.json [5] => more.json [6] => thrillist ) [pandora] => Array ( [0] => search.json )
```



Optional parameters
    params         - array[string] An array of Solr parameters. Refer to [Solr documentation](http://wiki.apache.org/solr/CommonQueryParameters) for specific queries.






     * Example the 'q' parameter would be passed as: `params[q]="*:*"`
     * A 'sort' parameter would be passed as: `params[sort]="price asc"`


Response
    result           - object Query info
        responseHeader - object Response info
            status                  - int Query status            QTime                 - int Query time
            params                - object Query params
        response   - object Response object            numFound           - int Number of documents found
            start                    - int Offset
            docs                    - array[object] Array of documents returned from Solr
        
**Sample GET request:**

        https://dev.jitr.jackthreads.com/services/v1/solr/?oauth_token=fad0d569aff38d59773e61cc78fbc016&core=product_indexer&searchHandler=search.json&params[q]=parent_product_id:152430



Sample Request to fetch products that are on sale now on JT.com with inventory:
        curl -sd "oauth_token=<token>&core=product_indexer&searchHandler=search.json&q=availability_start_1%3A%5B*+TO+NOW%2FMINUTES%5D+AND+availability_end_date_1%3A%5BNOW%2B1MINUTES%2FMINUTES+TO+*%5D&params%5Bfacet%5D=off&params%5BomitHeader%5D=true&params%5Bfq%5D=primary_in_stock_1%3A1" "https://api.jackthreads.com/services/v1/solr"


Example request
        curl --data "oauth_token=981a311208543683f06f12fe49db2715&core=product_indexer&searchHandler=search.json" https://api.jackthreads.com/services/v1/solr

Example response

        { "success": true, "errors": [], "result": { "responseHeader": { "status": 0, "QTime": 14, "params": { "echoParams": "all", "json.nl": "map", "wt": "json", "start": "0", "q": "*:*", "rows": "10" } }, "response": { "numFound": 205448, "start": 0, "docs": [ { "display_entity.is_active": true, "display_entity.entity_class": "Sale", "display_entity.single_width": true, "display_location.nav_url": "/offerings", "display_entities_schedule.position": 13, "display_schedule.name": "2013-12-23", "display_schedule.end_date": "2013-12-23T23:00:00Z", "display_entity.name": "Sophisticated City Boots", "display_schedule.id": 4418, "display_location.shop_id": 1, "display_entities_schedule.is_active": true, "display_location.nav_title": "Today's Sales", "display_schedule.start_date": "2013-12-23T17:00:00Z", "display_location.nav_subtitle": "The freshest new sales - updated daily", "display_entity.artemis_id": 1151182, "display_entity.id": 20862, "display_location.name": "Current Sale", "display_location.code": "sale", "display_entities_schedule.id": 177506, "display_entity.data": "", "display_location.id": "1", "sale.end_date": "2013-12-25T17:00:00Z", "sale.name": "Premium Leather Boots ft. Rogue", "sale_type.id": 7, "sale.shop_id": 1, "sale_element.show_timer": true, "sale_type.name": "Standard", "sale.is_active": true, "sale.start_date": "2013-12-22T17:00:00Z", "sale.url": "/sales/premium-leather-boots-ft-rogue/12496", "sale.id": 12496, "sale.display_entity.single_width": true, "sale.display_entity.id": 20862, "sale.display_entity.artemis_id": 1151182, "sale.display_entity.is_active": true, "sale.display_entity.name": "Sophisticated City Boots", "sale.display_entity.data": "" }, { "display_entity.is_active": true, "display_entity.entity_class": "Sale", "display_entity.single_width": true, "display_location.nav_url": "/offerings", "display_entities_schedule.position": 10, "display_schedule.name": "2013-12-23", "display_schedule.end_date": "2013-12-23T23:00:00Z", "display_entity.name": "Back by Popular Demand", "display_schedule.id": 4418, "display_location.shop_id": 1, "display_entities_schedule.is_active": true, "display_location.nav_title": "Today's Sales", "display_schedule.start_date": "2013-12-23T17:00:00Z", "display_location.nav_subtitle": "The freshest new sales - updated daily", "display_entity.artemis_id": 1151276, "display_entity.id": 20869, "display_location.name": "Current Sale", "display_location.code": "sale", "display_entities_schedule.id": 177524, "display_entity.data": "", "display_location.id": "1", "sale.end_date": "2013-12-26T17:00:00Z", "sale.name": "RESTOCKED: Found Object Bags & More", "sale_type.id": 7, "sale.shop_id": 1, "sale_element.show_timer": true, "sale_type.name": "Standard", "sale.is_active": true, "sale.start_date": "2013-12-23T17:00:00Z", "sale.url": "/sales/restocked-found-object-bags-more/12500", "sale.id": 12500, "sale.display_entity.single_width": true, "sale.display_entity.id": 20869, "sale.display_entity.artemis_id": 1151276, "sale.display_entity.is_active": true, "sale.display_entity.name": "Back by Popular Demand", "sale.display_entity.data": "" }
                    ]
        }
}