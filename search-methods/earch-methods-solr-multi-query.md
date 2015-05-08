Solr Query passthru


**HTTP Method**: GET or POST /services/v1/solr/mq (GET requests will be cached at the CDN, POSTs will not)
**Client Authorization**: Yes
**User Authorization**: No
**TLS**: Yes


**Solr Core + Search Handler Whitelist**

```
        [product_indexer] => Array
```
```
         ( [0] => search.json [1] => dsearch.json [2] => autocomplete.json [3] => suggest.json ) [mosaic] => Array ( [0] => find.json ) [metaverse] => Array ( [0] => find.json ) [hyperion] => Array ( [0] => suggest.json [1] => terms.json [2] => search.json [3] => get.json [4] => instant.json [5] => more.json [6] => thrillist ) [pandora] => Array ( [0] => search.json )
```



**Required Parameters**

    **queries** - *array* An array of query objects, each containing the following:

        **core** - *string* Solr core to run the query against

        **searchHandler** - *string* Solr endpoint to run the query against

        **key** - *string* The key in the response object that will contain the results

        **params** - *array* An array of Solr parameters.  Currently fq and facet.field need to be passed in as an array


**Sample GET Request**

        curl -s "https://dev.jitr.jackthreads.com/services/v1/solr/mq?oauth_token=52adcea226a43bff3da7d9bb664e7364&queries%5B0%5D%5Bkey%5D=sale&queries%5B0%5D%5Bcore%5D=metaverse&queries%5B0%5D%5BsearchHandler%5D=find.json&queries%5B0%5D%5Bparams%5D%5BomitHeader%5D=true&queries%5B0%5D%5Bparams%5D%5Bq%5D=sale.id:15153"


**Sample POST Request**


        curl -skd "oauth_token=3170b540fc2dcd2dfd00c1356d0ea74d&queries[0][key]=departments&queries[0][core]=metaverse&queries[0][searchHandler]=find.json&queries[0][params][q]=meta.type:department&queries[0][params][rows]=5&queries[1][key]=categories&queries[1][core]=metaverse&queries[1][searchHandler]=find.json&queries[1][params][q]=meta.type:category&queries[1][params][rows]=5" "https://dev.jitr.jackthreads.com/services/v1/solr/mq"


**You can also pass post data as JSON if the correct header is set:**

        curl -skd '`{`
          "queries":[
            {
              "core":"metaverse",
              "searchHandler":"find.json",
              "key":"departments",
              "params":{
                "q":"meta.type:department"
              }
            },
            {
              "core":"metaverse",
              "searchHandler":"find.json",
              "key":"departments",
              "params":{
                "q":"meta.type:department"
              }
            }
          ]
        }`' **-H "Content-Type: application/json"** "https://stage-jitr-00.jackthreads.com/services/v1/solr/mq?`oauth_token=0fbacd5c3743662d3b4b9862d52f195c"


**Sample Response**

        
{
  "success":true,
  "departments":{
    "success":true,
    "core":"metaverse",
    "url":"\/solr\/metaverse\/find.json?q=meta.type%3Adepartment&rows=5",
    "response":{
      "numFound":5,
      "start":0,
      "docs":[
        {
          "meta.id":"department_1",
          "meta.type":"department",
          "department.id":1,
          "department.name":"Accessories",
          "department.weight":3,
          "department.euc":"EUC-09020802",
          "department.page_title":"Accessories for Men - Real Fashion Furnishings for Guys",
          "department.page_description":"Check out the select styles of men's accessories exclusively on JackThreads, the online shopping community that delivers the best accessories, furnishings, gifts, & gadgets at members-only prices.",
          "department.slug":"accessories",
          "department.article_department.article_id":"3876848",
          "_version_":1486402263057432576
        },
        ...
      ]
    }
  },
  "categories":{
    "success":true,
    "core":"metaverse",
    "url":"\/solr\/metaverse\/find.json?q=meta.type%3Acategory&rows=5",
    "response":{
      "numFound":307,
      "start":0,
      "docs":[
        {
          "meta.id":"category_1",
          "meta.type":"category",
          "category.id":1,
          "category.name":"Contemporary",
          "category.category_class_id":1,
          "category.slug":"contemporary",
          "category.is_displayed":true,
          "category.rank":9999999,
          "_version_":1486402267025244160
        },
        ...
      ]
    }
  }
}