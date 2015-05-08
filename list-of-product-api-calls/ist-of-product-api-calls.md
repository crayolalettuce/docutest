These do not include transactional calls such as getting the cart, order totals, or refunds, just calls that list products such as products by brand.
 
BRANDS
=========
api_v1_products_by_brand_solr

CATEGORY
=========
% api_v1_get_products_with_category  - likely deprecated, 404s
api_v1_get_category_solr 
DEPARTMENTS
=========
% api_v1_products_in_department - likely deprecated
api_v1_products_in_department_solr

FEEDS
=========
* 
PRODUCTS
=========
api_v1_get_product 
SALES
=========
api_v1_get_product
api_v1_featured_item - likely deprecated, just returns 'success: true'
api_v1_get_sale_solr
api_v1_top_products
% api_v1_get_sale - deprecated, there is no endpoint that calls this
% api_active_sales - times out, likely deprecated
%api_v1_get_sale_filtered_by_brand - deprecated, use brand api call instead
%api_v1_get_sale_filtered_by_department - deprecated
%api_v1_get_sale_filtered_by_category - deprecated, use category api call
%api_v1_get_sale_filtered_by_color - deprecated
%api_v1_get_sale_filtered_by_size - deprecated
%api_v1_product_sale_update_view - deprecated 
SEARCH
=========
api_v1_product_search 
SOLR
=========
*