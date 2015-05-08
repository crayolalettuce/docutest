Edits a display entity


**HTTP method**: POST /services/v1/display_entities/:display_entity_id/edit

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**URL Parameters**:
    :display_entity_id - id of the display entity to edit

**Required Parameters**:
    none


**Optional Parameters**:
    name - string - name of the display entity, also updates the link name if it is a link entity aka "content box"
    url - string - url the image points to
    artemis_id - int - artemis id of the image used in the entity


    entity_type - string - one of: [image, link, video].

   ** required parameters depending on entity_type if entity_type is passed, and if the parameters do not already exist on the entity:**


       *image*

           artemis_id - int - artemis id of the image for the entity
           url - string - url the image points to

           name - string - name of the entity
       *video*

           video_url - string - url to the video

       *link*
*           *url - string - url the link points to

           name - string - text of the link entity
    



**Sample Request:**

curl -d "name='cool beans'&artemis_id=111222&url='sales/12354/15125'" https://dev.jitr.jackthreads.com/services/v1/display_entities/11451/edit 


**Sample Response:**


        {
            "success": true,
            "data": {
                "DisplayEntity": {
                    "id": "1234",
                    "name": "cool beans",
                    "entity_class": "Sale",
                    "entity_id": "1901",
                    "entity_type": "sale",
                    "data": "22c05c26520452f9e791e9648185ee84.jpg",
                    "is_active": true,
                    "single_width": false,
                    "artemis_id": "111222"
                },
                "Sale": {
                    "id": "1901",
                    "name": "Creative Recreation",
                    "start_date": "2011-01-01 12:00:00",
                    "end_date": "2011-01-08 12:00:00",
                    "shop_id": "1",
                    "sale_type_id": "7",
                    "sale_template_id": "1",
                    "is_active": true,
                    "is_final": false,
                    "refund_cash": false,
                    "refund_cash_exception": false,
                    "in_stock": true,
                    "created": "2010-12-30 08:45:12",
                    "modified": "2013-05-30 09:54:00",
                    "est_ship_start": null,
                    "est_ship_end": null,
                    "quantity_tracked": true,
                    "is_locked": false,
                    "url_friendly_name": null,
                    "url": "/sales/creative-recreation/1901",
                    "url_sale_expired": "/",
                    "related_sale_ids": null
                },
                "Link": {
                    "id": null,
                    "name": null,
                    "url": null
                },
                "DisplaySchedule": [
                    {
                        "id": "417",
                        "name": "2011-01-01",
                        "start_date": "2011-01-01 12:00:00",
                        "end_date": "2011-01-02 12:00:00",
                        "display_location_id": "1",
                        "artemis_id": null,
                        "DisplayEntitiesSchedule": {
                            "id": "3924",
                            "display_schedule_id": "417",
                            "display_entity_id": "1234",
                            "position": "1",
                            "is_active": true,
                            "target": null
                        }
                    }
                ]
            },
            "errors": [],
            "currency": {
                "code": "USD",
                "symbol": "$",
                "name": "US Dollar",
                "locale": "US"
            }
        }