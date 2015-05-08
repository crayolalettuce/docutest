Removes all entities attached to a schedule and associates the newly passed entities


**HTTP method**: POST /services/v1/display_schedules/:display_schedule_id/relink

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**URL Parameters**:
    :display_schedule_id - id of the display schedule to associate passed display entities with

**Required Parameters**:
    display_entities - array - array of JSON objects consisting of display entity information

**Display_entities Parameters**:
    id - int - id of the display entity

    position - int - position of the display entity within the schedule, must be distinct for all entities in the passed array

    target - string - [OPTIONAL] - "_new" if the entity should open a new window when clicked, defaults to null


**Sample Request:**

curl -d "display_entities=[{'id':'124', 'position':'100'},{'id':'123', 'position':'2'}]" "https://dev.jitr.jackthreads.com/services/v1/display_schedules/11451/relink" 


**Sample Response:**


        {
            "success": true,
            "data": {
                "DisplaySchedule": {
                    "id": "11451",
                    "name": "2015-01-30",
                    "start_date": "2015-01-30 12:00:00",
                    "end_date": "2015-01-31 12:00:00",
                    "display_location_id": "1",
                    "artemis_id": null
                },
                "DisplayLocation": {
                    "id": "1",
                    "code": "sale",
                    "name": "Current Sale",
                    "nav_title": "Today's Sales",
                    "nav_subtitle": "The freshest new sales - updated daily",
                    "nav_url": "/offerings",
                    "shop_id": "1",
                    "display_admin": true
                },
                "DisplayEntity": [
                    {
                        "id": "123",
                        "name": "Army Brand   Sub Sale 03/28",
                        "entity_class": "Sale",
                        "entity_id": "1045",
                        "entity_type": "sale",
                        "data": "c0802b534079e14f7cce46af6e07875c.jpg",
                        "is_active": true,
                        "single_width": false,
                        "artemis_id": "99571",
                        "DisplayEntitiesSchedule": {
                            "id": "357191",
                            "display_schedule_id": "11451",
                            "display_entity_id": "123",
                            "position": "2",
                            "is_active": true,
                            "target": null
                        }
                    },
                    {
                        "id": "124",
                        "name": "Sneaker   Sub Sale 03/29",
                        "entity_class": "Sale",
                        "entity_id": "1046",
                        "entity_type": "sale",
                        "data": "d782f280bfd5ca119c7ef979b6b526ef.jpg",
                        "is_active": true,
                        "single_width": false,
                        "artemis_id": "99572",
                        "DisplayEntitiesSchedule": {
                            "id": "357190",
                            "display_schedule_id": "11451",
                            "display_entity_id": "124",
                            "position": "100",
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