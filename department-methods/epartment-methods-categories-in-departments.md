Get a list of categories with products on sale in each department


HTTP method: GET /services/v1/departments_categories
Client authorization: no
User authorization: no
TLS: no


**Response**:
categories - list
    department_id - string

    department_name - string

    categories - list

        id - int Category id

        name - string Category name

        img_url - string Image url

        total_products - int Count of products available in the category



**Example Request:**

        curl http://16.camp.jackthreads.com:9016/services/v1/departments_categories
        

**Example Response:**


        {
          "success":true,
          "categories":[
            {
              "department_id":"1",
              "department_name":"Accessories",
              "categories":[
                {
                  "id":14,
                  "name":"Bags",
                  "img_url":"http:\/\/ak-images.jackthreads.com\/v1\/image\/720562",
                  "total_products":92
                },
                {
                  "id":167,
                  "name":"Cold Weather",
                  "img_url":"http:\/\/ak-images.jackthreads.com\/v1\/image\/720566",
                  "total_products":43
                },...
              ]
            }, ...
          ]
        }