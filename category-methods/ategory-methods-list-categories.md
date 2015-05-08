Get a list of categories.

HTTP method: GET /services/v1/categories
Client authorization: no
User authorization: no
TLS: no


**Optional parameters**

        with_products - bool Include number of on-sale products for each category in response
        with_icons - bool Include icon image URIs in response

Response
 categories  - array List of categories
  id   - integer Category ID
  name   - string Name
                icon - string (Included only if with_icons provided) Icon image URI

                total_products - integer (Included only if with_products provided) Total number of products available for sale



**Example request**

        curl http://16.camp.jackthreads.com:9016/services/v1/categories?with_products=1&with_icons=1

Example response

        

{
   "success":true,
   "categories":[
      {
         "id":4,
         "name":"Tees and Tanks",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-4.png"
      },
      {
         "id":5,
         "name":"Sweatshirts",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-5.png"
      },
      {
         "id":6,
         "name":"Shirts",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-6.png"
      },
      {
         "id":7,
         "name":"Sweaters",
         "total_products":16,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-7.png"
      },
      {
         "id":8,
         "name":"Denim and Pants",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-8.png"
      },
      {
         "id":9,
         "name":"Shorts",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-9.png"
      },
      {
         "id":10,
         "name":"Jackets",
         "total_products":6,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-10.png"
      },
      {
         "id":11,
         "name":"Music",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-11.png"
      },
      {
         "id":12,
         "name":"Watches",
         "total_products":35,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-12.png"
      },
      {
         "id":13,
         "name":"Sunglasses",
         "total_products":4,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-13.png"
      },
      {
         "id":14,
         "name":"Bags",
         "total_products":2,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-14.png"
      },
      {
         "id":15,
         "name":"Mens Furnishings",
         "total_products":4,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-15.png"
      },
      {
         "id":16,
         "name":"Basics",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-16.png"
      },
      {
         "id":17,
         "name":"Hats",
         "total_products":6,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-17.png"
      },
      {
         "id":18,
         "name":"Jewelry",
         "total_products":3,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-18.png"
      },
      {
         "id":19,
         "name":"Gifts and Gadgets",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-19.png"
      },
      {
         "id":116,
         "name":"Footwear",
         "total_products":6,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-116.png"
      },
      {
         "id":127,
         "name":"Vests",
         "total_products":0,
         "icon":"http:\/\/16.camp.jackthreads.com:9016\/data\/api\/icons\/category-127.png"
      }
   ]
}