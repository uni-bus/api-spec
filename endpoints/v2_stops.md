# Uni Bus API Endpoints

## Usage

Please [see the README for more information](../README.md) about using this API.

## Common API Parameters

Please [see this document](v2_common.md) for Common Parameters required as part of the request.

## Stops

**GET** `/v2/{university}/stops`

Returns all of the Bus Stops which have Scheduled Bus Services for this University.

Sample Response:

```json
{
  "stops": [
    {
      "id": 1,
      "name": "Letojanni",
      "description": "Letojanni",
      "latitude": 37.878952,
      "longitude": 15.305295,
      "is_university": false,
      "is_on_way_to_university": true,
      "is_on_way_home": true,
      "last_updated": "2017-01-01T09:00:00Z"
    },
    {
      "id": 2,
      "name": "Taormina",
      "description": "Taormina Centro",
      "latitude": 37.855123,
      "longitude": 15.289179,
      "is_university": false,
      "is_on_way_to_university": true,
      "is_on_way_home": true,
      "last_updated": "2017-01-01T09:00:00Z"
    }
  ]
}
```
~> **NOTE:** the field `last_updated` is currently always returned in UTC. A future version of this endpoint will support timezones.
