Creates or clones a display schedule


**HTTP method**: POST /services/v1/display_schedules/create

**Client authorization**: No
**User authorization**: Yes
**TLS**: Yes


**Required Parameters**:
    id - int - id of a display schedule to clone

OR
    start_date - string - time representing the start of the schedule
    display_location_id - int - display location of the schedule



**Optional Parameters**:
    name - string - name of the schedule. defaults to 'YYYY-mm-dd' of the start date of the schedule.



**Sample Request:**

curl -d "id=12" "https://dev.jitr.jackthreads.com/services/v1/display_schedules/create" 


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