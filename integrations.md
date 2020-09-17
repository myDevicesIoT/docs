# Supported Integrations
 - Azure IoT Hub
 - Azure Service Bus
 - Azure Event Hubs
 - Azure Storage
 - Azure IoT Central
 - PowerBI
 - Amadeus HotSOS
 - ARM Treasure Data
 - AWS Kinesis
 - AWS S3
 - AWS SQS
 - Google PubSub
 - Google BigQuery
 - Google Storage
 - Google Sheets
 - Slack
 - Discord
 - Salesforce
 - PagerDuty
 - Zendesk
 
## Example Payloads
 - [Uplink Event JSON](#example-uplink-event-json)
 - [Alert Event JSON](#example-alert-event-json)

#### Example Uplink Event JSON

```json
{
    "event_type": "uplink",
    "event_data": {
        "device_id": "f149f990-f8bb-11e8-9adb-a53XXa229d",
        "user_id": "8f48fbfe-289e-430e-9320-26XXac47414",
        "payload": [
            {
                "channel": 100,
                "name": "RSSI",
                "sensor_id": "f17d1780-f8bb-1XX8-9adb-a53ca5ca229d",
                "type": "rssi",
                "unit": "dbm",
                "value": -30
            },
            {
                "channel": 101,
                "name": "SNR",
                "sensor_id": null,
                "type": "snr",
                "unit": "db",
                "value": 8.3
            },
            {
                "channel": 3,
                "name": "Internal Temp",
                "sensor_id": "f17cf070-f8bb-11XX-9XXb-a53ca5ca229d",
                "type": "temp",
                "unit": "c",
                "value": 22.1
            },
            {
                "channel": 4,
                "name": "Humidity",
                "sensor_id": "f17c7b40-f8bb-11XX-9adb-a53ca5ca229d",
                "type": "rel_hum",
                "unit": "p",
                "value": 30
            },
            {
                "channel": 5,
                "name": "Battery",
                "sensor_id": "f17d65a0-f8bb-1XX-8fe8-01629cf04bf7",
                "type": "batt",
                "unit": "p",
                "value": 100
            },
            {
                "channel": 7,
                "name": "Probe Temp",
                "sensor_id": "f17d3e90-f8bb-11XX-8fe8-01629cf04bf7",
                "type": "temp",
                "unit": "c",
                "value": 22.6
            }
        ],
        "topic": "v1/d4551a40-f8bb-1XX8-9adb-a53ca5ca229d/things/f149f990-f8bb-11e8-9adb-a53ca5ca229d/data/json",
        "channel": "json",
        "client_id": "d4551a40-f8bb-11XX-9adb-a53ca5ca229d",
        "hardware_id": "001a380000800XXX",
        "timestamp": 1544037693831,
        "application_id": "iotinabox"
    },
    "company": {
        "address": "3333 Arapahoe Rd",
        "city": "Erie",
        "country": "United States",
        "created_at": "2018-12-05T18:30:30.000Z",
        "id": 136,
        "industry": "[\"Food & Beverage\"]",
        "latitude": 40.0169468,
        "longitude": -105.1008409,
        "name": "Safeway",
        "state": "CO",
        "status": 0,
        "timezone": "America/Denver",
        "updated_at": "2018-12-05T18:30:30.000Z",
        "user_id": "8f48fbfe-289e-430e-9320-2621eaXX14",
        "zip": "80516"
    },
    "device": {
        "created_at": "2018-12-05T18:31:13.000Z",
        "id": 1253,
        "status": 0,
        "updated_at": "2018-12-05T18:31:13.000Z"
    },
    "device_type": {
        "application_id": null,
        "category": "module",
        "codec": "lorawan.sanmina.th",
        "created_at": "2018-04-04T15:37:42.000Z",
        "data_type": null,
        "description": "Sanmina Temperature/Humidity Sensor",
        "id": "1d54c830-381e-11e8-b72a-ed664XX4faad",
        "manufacturer": "Sanmina",
        "model": "Temperature/Humidity",
        "name": "Sanmina - IoT in a Box",
        "parent_constraint": "NOT_ALLOWED",
        "proxy_handler": "PrometheusClient",
        "subcategory": "lora",
        "transport_protocol": "lorawan",
        "updated_at": "2018-04-04T15:37:42.000Z",
        "version": null
    },
    "location": {
        "address": "3333 Arapahoe Rd",
        "city": "Erie",
        "company_id": 136,
        "country": "United States",
        "created_at": "2018-12-05T18:30:31.000Z",
        "id": 152,
        "industry": "[\"Food & Beverage\"]",
        "latitude": 40.0169468,
        "longitude": -105.1008409,
        "name": "Safeway",
        "state": "CO",
        "status": 0,
        "timezone": "America/Denver",
        "updated_at": "2018-12-05T18:49:44.000Z",
        "user_id": "8f48fbfe-289e-430e-9320-26XXXc47414",
        "zip": "80516"
    }
}
```

#### Example Alert Event JSON

```json
{
    "event_type": "alert",
    "event_data": {
        "userId": "10e0a25d-d879-4380-b8fc-4bbf02ee50e2",
        "applicationId": "iotinabox",
        "clientId": "0a4232a0-1833-11e9-98fe-310X2d642d7",
        "thingId": "1f7c0420-1f40-11e9-a086-7bX4cc88e77",
        "sensorId": "1f91af00-1f40-11e9-a086-7bdXc88e77",
        "ruleId": "5c48b81d101b276bf4a1efbe",
        "eventType": "alert-state-changed",
        "totalTriggered": 4,
        "hardwareId": "00137a1000000XXX",
        "triggered": true,
        "value": 1,
        "timestamp": "1548692292944",
        "triggerData": {
            "delay": {
                "count": 1,
                "time": 600000
            },
            "trigger_reading": 1,
            "trigger_type": "trigger",
            "trigger_unit": "d",
            "triggers": [
                {
                    "conditions": [
                        {
                            "operator": "eq",
                            "value": 1
                        }
                    ],
                    "trigger_reading": 1,
                    "trigger_unit": "d",
                    "triggers_combination": "OR"
                }
            ],
            "triggers_combination": "OR"
        }
    },
    "company": {
        "address": "687 S Asdf",
        "city": "Erie",
        "country": "United States",
        "created_at": "2019-01-14T19:31:57.000Z",
        "id": 250,
        "industry": "[\"Food & Beverage\"]",
        "latitude": 40.0339685,
        "longitude": -105.0640296,
        "name": "SecondCo",
        "state": "CO",
        "status": 0,
        "timezone": "America/Denver",
        "updated_at": "2019-01-14T19:31:57.000Z",
        "user_id": "10e0a25d-d879-4380-b8fc-4bXX2ee50e2",
        "zip": "80516"
    },
    "device": {
        "created_at": "2019-01-23T18:53:08.000Z",
        "id": 4313,
        "status": 0,
        "updated_at": "2019-01-23T18:53:08.000Z"
    },
    "device_type": {
        "application_id": null,
        "category": "module",
        "codec": "lorawan.netvox.motion",
        "created_at": "2017-12-28T17:40:44.000Z",
        "data_type": null,
        "description": "Netvox Motion sensor",
        "id": "121f5944-e52b-11e7-80c1-9a214cfXXXae",
        "manufacturer": "Netvox ",
        "model": null,
        "name": "Netvox Motion - IoT in a Box",
        "parent_constraint": "NOT_ALLOWED",
        "proxy_handler": "PrometheusClient",
        "subcategory": "lora",
        "transport_protocol": "lorawan",
        "updated_at": "2018-04-04T00:22:36.000Z",
        "version": "1.0"
    },
    "location": {
        "address": "687 S Asdf",
        "city": "Erie",
        "company_id": 250,
        "country": "United States",
        "created_at": "2019-01-14T19:31:58.000Z",
        "id": 270,
        "industry": "[\"Food & Beverage\"]",
        "latitude": 40.0339685,
        "longitude": -105.0640296,
        "name": "SecondLoc",
        "state": "CO",
        "status": 0,
        "timezone": "America/Denver",
        "updated_at": "2019-01-18T17:31:08.000Z",
        "user_id": "10e0a25d-d879-4380-b8fc-4bbf02eXXe2",
        "zip": "80516"
    }
}
```
