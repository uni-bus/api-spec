# Uni Bus API Endpoints

## Usage

Please [see the README for more information](../README.md) about using this API.

## Common API Parameters

Please [see this document](v2_common.md) for Common Parameters required as part of the request.

## Departures from Stop

**POST** `/v2/{university}/departures`

Returns information about the next departures from a given Bus Stop.

Request:

```json
{
  "departure_date": "2018-01-01T01:02:03Z",
  "max_results": 5,
  "stop_id": 1
}
```

* `departure_date` - (Required) A RFC3339 formatted date of when the user would like departure information from (this should generally be the current date).

~> **NOTE:** the field `departure_date` must currently be sent in UTC. A future version of this endpoint will support timezones.

* `stop_id` - (Required) The ID of the Bus Stop to return departures from.

* `max_results` - (Optional) The maximum number of departures which should be returned. Defaults to `5` with a max of `10`.

Response:

```json
{
  "departures": [
    {
      "service": {
        "service": {
          "id": 97872,
          "name": "Route A",
          "start_stop_id": 1,
          "end_stop_id": 3,
          "start": "2018-06-16T02:00:00Z",
          "end": "2018-06-16T02:45:00Z"
        },
        "stops": [
          {
            "id": 461259,
            "bus_service_id": 97872,
            "stop_id": 1,
            "arrival": "2018-06-16T02:00:00Z",
            "departure": "2018-06-16T02:00:00Z",
          },
          {
            "id": 461260,
            "bus_service_id": 97872,
            "stop_id": 2,
            "arrival": "2018-06-16T02:25:00Z",
            "departure": "2018-06-16T02:25:00Z"
          },
          {
            "id": 461261,
            "bus_service_id": 97872,
            "stop_id": 3,
            "arrival": "2018-06-16T02:45:00Z",
            "departure": "2018-06-16T02:45:00Z"
          }
        ],
      },
      "departure_time": "2018-06-16T02:00:00Z",
      "arrival_time": "2018-06-16T02:00:00Z"
    }
  ]
}
```

~> **NOTE:** the fields `departure_time`, `arrival_time`, `departure` and `arrival` are currently returned in UTC. A future version of this endpoint will support timezones.
