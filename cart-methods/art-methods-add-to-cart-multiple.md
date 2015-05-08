Add a given item in the given sale to the user’s cart.

HTTP method: POST /services/v1/cart/add_multiple
Client authorization: no
User authorization: required
TLS: required

Required parameters
**    
**    items  - array Array of the following:


        
        Required parameters    
        One of:
        sku  - string SKU
        option_id - integer Product option ID

        Optional parameters
**

**        qty          - integer Number of items to add (default: 1)
        sale_id         - integer Sale ID (default: 0)
        object_type     - string Page names/App views (e.g.: Product/Sale/Dept/Category/Article/etc)

        object_id         - integer ID of the object_type passed (e.g. 123)

        unit                  - string Smaller unit inside 'object_type' (e.g.: Quickbuy, RichRelevance, RightRail, ProductUnit)


        position_within_unit         - integer ID of the unit passed (e.g. 123)


        url                    - string (e.g.: http://www.jackthreads.com/home/artwork/249)


        source            - string source device (web (default) / mobile-web / iphone / ipad / android)

        shop_id         - integer ID of the shop (default: 1 (jackthreads) / 2 (thrillist shop) / 4 (supercompressor shop) )


**Sample Request**

**

**

curl -v --data "oauth_token=ad33bf91a7a2aa05a5a97ead17435a92&items=[{\"option_id\":608567}, {\"option_id\":12346}]" https://stage-jitr-00-jt.jackthreads.com/services/v1/cart/add_multiple




Sample Response
{"qty": 1,"req_qty": 2,"errors": {"code": "out_of_stock"},"items": {"12346": {"success": true,"errors": [],"qty": 0,"req_qty": 1,"id": 12346},"608567": {"success": true,"errors": [],"qty": 1,"req_qty": 1,"id": 608567}},"success": false,"cart": {"qty": 1,"expired": 0,"subtotal": "40.00","shipping": "0.00","customs": "0.00","tax": "0.00","discount": "0.00","store_credit": "0.00","gift_card": "0.00","coupon_discount": "10.00","coupons": [{"id": 1,"name": "employee","type": "percent","method": "auto","amount": "10.00","desc": "Employee Discount","show": true}],"total": "30.00","retail": "40.00","saved": "0.00","items": [{"id": 608567,"sku": "JT00608567","cart_id": 50000030,"product_id": 173260,"name": "Kransen In-Ear Headphones Indigo","display_name": "Urban Ears Kransen In-Ear Headphones Indigo","expires": "2015-04-13 15:24:30","price": "40.00","image": "[http://ak-images.jackthreads.com/v1/image/1447779](http://ak-images.jackthreads.com/v1/image/1447779)","url": "/urban-ears/music/kransen-in-ear-headphones-indigo/products/173260","brand": {"id": 293,"name": "Urban Ears"},"color": {"id": 1784,"name": "Indigo"},"size": {"id": 140,"name": "One Size"},"sale": {"id": 0,"name": null,"start_date": null,"end_date": null},"qty": 1,"is_expired": false,"is_returnable": true,"refund_cash": true,"promo_exclusions": [],"has_promo_exclusion": false,"is_virtual": false,"est_delivery": "April 20th 2015 to April 25th 2015","shop_id": "1","discount_price": null,"coupon_sale_id": null}],"estimated_delivery": "April 20th 2015 to April 25th 2015","cart_expiration": "2015-04-13 15:24:30","cart_lifetime": "5","instock": true,"shipping_exclusions": null,"formatted_summary": [{"label": "Subtotal","value": "$40.00","neg": false},{"label": "Employee Discount","value": "$10.00","neg": true},{"label": "Total","value": "$30.00","neg": false}],"formattedText": "Subtotal: $40.00\nEmployee Discount: $10.00\nTotal: $30.00","time_now": 1428952772},"added_qty": 1,"currency": {"code": "USD","symbol": "$","name": "US Dollar","locale": "US"}}