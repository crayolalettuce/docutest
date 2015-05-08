Creates or clones a display entity. This is a crazy call with 100 optional parameters 



**HTTP method**: POST /services/v1/display_entities/create

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**Required Parameters**:
    id - int - id of the display entity to clone

        OR

    url - string - link url for the entity
    name - string - name of the entity
    entity_type - string - one of: [image, link, video].

   ** extra parameters depending on entity_type:**


       *image*

           artemis_id - int - artemis id of the image for the entity
       *video*

           video_url - string - url to the video

       *link*

           [OPTIONAL] artemis_id - int - artemis id of the image for the entity



**Optional Parameters**:
    sale_id - int - sale to attach the entity to. if not passed, creates a new link entity, aka "content box"



**Sample Request:**

curl -kd "artemis_id=1111111&entity_type='link'&url='sales/cool-sale/12345'&name='cool beans'&artemis_id=111222" https://dev.jitr.jackthreads.com/services/v1/display_entities/create


**Sample Response:**


        {
            "success": true,
            "data": {
                "DisplayEntity": {
                    "id": "30629",
                    "name": "cool beans",
                    "entity_class": "Link",
                    "entity_id": "3078",
                    "entity_type": "link",
                    "data": null,
                    "is_active": true,
                    "single_width": false,
                    "artemis_id": "111222"
                },
                "Sale": {
                    "id": null,
                    "name": null,
                    "start_date": null,
                    "end_date": null,
                    "shop_id": null,
                    "sale_type_id": null,
                    "sale_template_id": null,
                    "is_active": null,
                    "is_final": null,
                    "refund_cash": null,
                    "refund_cash_exception": null,
                    "in_stock": null,
                    "created": null,
                    "modified": null,
                    "est_ship_start": null,
                    "est_ship_end": null,
                    "quantity_tracked": null,
                    "is_locked": null,
                    "url_friendly_name": null,
                    "url": null,
                    "url_sale_expired": null,
                    "related_sale_ids": null
                },
                "Link": {
                    "id": "3078",
                    "name": "cool beans",
                    "url": "sales/12354/15125"
                },
                "DisplaySchedule": []
            },
            "errors": [],
            "currency": {
                "code": "USD",
                "symbol": "$",
                "name": "US Dollar",
                "locale": "US"
            }
        }