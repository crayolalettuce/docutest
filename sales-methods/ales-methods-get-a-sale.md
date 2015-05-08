Get products in a given sale.
 
 HTTP method: GET /services/v1/sales/<id>
 Client authorization: no
 User authorization: no
 TLS: no
 
 Required parameters 
**    **id - integer Sale ID 

  
**Optional parameters
     sort - string Sort parameter (either “sold” or “price”)
     order    - string Sort order (either “asc” or “desc”)** 
    offset - integer Offset, for pagination (first page is "0")
  
    limit       - integer Limit, for pagination
  

  Response 
    sale   - object Sale info 
        id   - integer Sale ID 
        name   - string Sale name 
        start_date  - string Start date 
        end_date          - string End date 
** 
<strike>est_delivery</strike>  - string Estimated delivery date (deprecated) ** 
        brands  - array List of brand info 
            id           - integer Brand ID 
            name   - string Brand name 
        sizes  - array List of size info 
            id           - integer Size ID 
            name   - string Size
        metadata        - object Metadata info

            vocabulary

                key_name: key value

        sale_element - object
id

title

body 
        products  - array List of products in the sale 
            id           - integer Product ID 
            name   - string Product name 
            price   - string JackThreads price 
            retail   - string Retail price 
            image   - string Image URI 
            almost_sold_out - boolean True if the product is almost sold out
  
            sold_out  - boolean True if the product is sold out 
            brand   - object Brand info 
                id           - integer Brand ID 
                name   - string Brand name 
** 
talent   - object Model information (null if none available) ** 
 
** 
 height   - string Models height 
 weight   - string Model’s weight 
 waist   - string Model’s waist size ** ** 
position   - integer **** 
 Buyer specified sort order field ** 
** 
categories - array List of categories ** 
 
** 
     id - integer Category ID 
     name - string Category name **  
            options   - array List of product options 
                id           - integer Product option ID 
                sku           - string SKU 
                sold_out                   - boolean True if this option is sold out 
                color                 - object Color info 
                    id               - integer Color ID 
                    code              - string Color code 
                    name              - string Color name 
                size                  - object Size info 
                    id               - integer Size ID 
                    code              - string Size code 
                    name              - string Size name
 
 Example request
 `curl http://16.camp.jackthreads.com:9016/services/v1/sales/3595`
 
 Example response
 
{
    "success":true,
    "sale":{
       "id":3595,
       "name":"Neff Watches",
       "start_date":"2011-09-11 12:00:00",
       "end_date":"2011-09-14 12:00:00",
       "est_delivery":"2012-01-03",
       "image":null,
       "brands":[
          {
             "id":"637",
             "name":"Neff Headwear"
          }
       ],
       "sizes":[
          {
             "id":"140",
             "name":"One Size"
          }
       ]`, `      `**"metadata"**:{ `            **"seo"**:{
                  "**page_title**":"Baseball Jerseys and Mens Jogger Pants"
            },
            **"merch"**:{
                  "**hide_rich_relevance**":"1"
            }
      },

                 "**sale_element**": {

                    "**id**":"1234",

                    "**title**":"Neff Watches",
                    "**body**":"`Elwood tees are all about the Big Picture.`"
                 }
    },
    "products":[
       {
          "id":32448,
          "name":"Flava Digital Watch Yellow",
          "price":"19.99",
          "retail":"20.00",
          "images":[
 
          ],
          "sold_out":true,
          "desc":null,
          "features":null,
          "weight":"2.0",
          "brand":{
             "id":637,
             "name":"Neff Headwear"
          },
          "options":[
             {
                "id":152047,
                "sku":"JT00152047",
                "color":{
                   "id":3077,
                   "code":null,
                   "name":"Yellow"
                },
                "size":{
                   "id":140,
                   "code":"OS",
                   "name":"One Size"
                }
             }
          ]
       },
       {
          "id":32449,
          "name":"Flava Digital Watch Orange",
          "price":"19.99",
          "retail":"20.00",
          "images":[
 
          ],
          "sold_out":true,
          "desc":null,
          "features":null,
          "weight":"2.0",
          "brand":{
             "id":637,
             "name":"Neff Headwear"
          },
          "options":[
             {
                "id":152048,
                "sku":"JT00152048",
                "color":{
                   "id":3520,
                   "code":null,
                   "name":"Orange"
                },
                "size":{
                   "id":140,
                   "code":"OS",
                   "name":"One Size"
                }
             }
          ]
       }
    ]
 } 
**

 ** 
[**Applying Filters:**]() 
The proper way to apply filters to these api calls is to: 
 
* Append "/filter/" to the original api url
 
 * http://api.jackthreads.com/services/v1/sales/12291 =>http://api.jackthreads.com/services/v1/sales/12291**/filter/**

 
 * For all of the filters being applied, grab their filter_parameter values, sort them alphabetically, and then append them to the urls separated by a '/'.  
 
 * To look for products in sale 12291 that are the color Black and in the Bags category, apply the color and category filter: *filter_parameter:"color_id:4" and filter_parameter:"category_id:14"*
  * Sorted: category_id:14, color_id:4
  * Appended to the api url:  http://api.jackthreads.com/services/v1/sales/12291/filter/**category_id:14/color_id:4**