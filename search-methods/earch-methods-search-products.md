Search for products currently on sale


HTTP method: POST /services/v1/search/products
Client authorization: No
User authorization: No
TLS: No


Required Parameters:
    q - string Search string


Optional Parameters:
    offset - int Offset for pagination, starting at "0"
    limit - int Max number of products in a response
    sort - string Sort parameter (price or sold)
    order - string Sort order ("asc" or "desc")
    fq[] - string Raw solr filter query

    locale - string 2 character country code for retrieving international prices
    replaceprice - boolean true to replace the 'price' field of products instead of appending converted values


Response:

{
  "success": true,`
`
"filters": 
{
"sort": 
[


    {
    "order": 0,
    "id": "price_low",
    "name": "Price Low-to-High",
    "url": ""
    },...
],

-
"brands": 
[


    {
    "id": 1441,
    "name": "3rd & Army",
    "url": ""
    },...
],

"categories": 
[
...],
-
"colors": 
[
...],
-
"departments": 
[
...],
-
"sizes": 
[
...]
-
},
-
"total_products": 224,
"total_sold_out_products": 0,
"products": 
[

{
"id": 107872,
"name": "Soma Sweater",
"price": "34.99",
"retail": "60.00",
"images": 
[(4)
"[http://ak-images.jackthreads.com/v1/image/646074](http://ak-images.jackthreads.com/v1/image/646074)",
"[http://ak-images.jackthreads.com/v1/image/646075](http://ak-images.jackthreads.com/v1/image/646075)",
"[http://ak-images.jackthreads.com/v1/image/646076](http://ak-images.jackthreads.com/v1/image/646076)",
"[http://ak-images.jackthreads.com/v1/image/646077](http://ak-images.jackthreads.com/v1/image/646077)"],
-
"sold_out": false,
"almost_sold_out": false,
"desc": "Soma Sweater by KR3W. 100% authentic KR3W merchandise.",
"features": "Color: Charcoal Heather Material: 100% Cotton Fit: True to size Ribbed cuffs and hem Drawstring hood Single kangaroo pocket Button placket ",
"weight": "1.00",
"position": 120,
"categories": 
[(2)

{
"id": 2,
"name": "Streetwear"
},
-

{
"id": 7,
"name": "Sweaters"
}
-],
-
"brand": 
{
"id": 20,
"name": "KR3W"
},
-
"department": 
{
"id": "2",
"name": "Clothing"
},
-
"talent": null,
"options": 
[(4)

{
"id": 375083,
"sku": "JT00375083",
"color": 
{
"id": 3,
"code": "Charcoal",
"name": "Charcoal"
},
-
"size": 
{
"id": 141,
"code": "S",
"name": "Small",
"rank": 55,
"department": "Clothing"
},
-
"sellable": true,
"in_stock_sellable": true,
"sold_out": false
},
-

{
...
},
-

{
...
},
-

{
...
}
-],
-
"runtype": 
[(0)],
"is_look_item": 0,
"sale": 
{
"id": 8780
}
-
}
]

}


To apply filters, see [this](jackthreads-v1-api-sales-methods-get-a-sale#filters).