Deletes a display schedule and fills any gaps this may cause


**HTTP method**: POST /services/v1/display_schedules/:display_schedule_id/delete

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**Required Parameters**:
    none


**Sample Request:**

curl "https://dev.jitr.jackthreads.com/services/v1/display_schedules/10800/delete" 


**Sample Response:**


        {
            "success": true,
            "data": {
                "DisplaySchedule": {
                    "id": "10800",
                    "name": "2009-12-03",
                    "start_date": "2009-12-03 12:00:00",
                    "end_date": "2009-12-04 12:00:00",
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
                        "id": "2335",
                        "name": "King Stampede Main Sale",
                        "entity_class": "Sale",
                        "entity_id": "854",
                        "entity_type": "sale",
                        "data": "96342001f5e5e8e35df7d743d65b5994.jpg",
                        "is_active": true,
                        "single_width": false,
                        "artemis_id": "101748",
                        "DisplayEntitiesSchedule": {
                            "id": "349827",
                            "display_schedule_id": "10800",
                            "display_entity_id": "2335",
                            "position": "1",
                            "is_active": true,
                            "target": null
                        }
                    },
                    {
                        "id": "2330",
                        "name": "Lifetime Collective Sub Sale",
                        "entity_class": "Sale",
                        "entity_id": "852",
                        "entity_type": "sale",
                        "data": "7425a6f03d0f18fb259434326e741a56.jpg",
                        "is_active": true,
                        "single_width": false,
                        "artemis_id": "101743",
                        "DisplayEntitiesSchedule": {
                            "id": "349828",
                            "display_schedule_id": "10800",
                            "display_entity_id": "2330",
                            "position": "2",
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