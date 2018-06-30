# Uni Bus API Endpoints

## Usage

Please [see the README for more information](../README.md) about using this API.

## Common API Parameters

Please [see this document](v2_common.md) for Common Parameters required as part of the request.

## Dashboard

**POST** `/v2/{university}/dashboard`

Returns information used on the Dashboard - namely the next Bus Service to and from University:

### Request

```json
{
  "home_departure_stop_id": 21,
  "university_destination_stop_id": 9,
  "university_departure_stop_id": 8,
  "home_destination_stop_id": 21,
  "departure_date": "2018-01-02T04:05:06Z",
  "max_results": 5
}
```

* `home_departure_stop_id` - (Required) The ID of the Bus Stop that the user departs from on their way to university.
* `university_destination_stop_id` - (Required) The ID of the Bus Stop the user gets off on the way to university.

* `university_departure_stop_id` - (Required) The ID of the Bus Stop the user departs from on the way home from university.
* `home_destination_stop_id` - (Required) The ID of the Bus Stop that the user gets off at on the way home from university.

* `departure_date` - (Required) A RFC3339 formatted date of when the user would like departure information from (this should generally be the current date).

~> **NOTE:** the field `departure_date` must currently be sent in UTC. A future version of this endpoint will support timezones.

* `max_results` - (Optional) The maximum number of results which can be returned. Defaults to `5` with a max of `10`.

### Response

```json
{
	"dashboard": {
		"journey_to_university": [{
			"service": {
				"service": {
					"id": 100221,
					"university_id": 1,
					"name": "Route A",
					"start_stop_id": 1,
					"end_stop_id": 3,
					"start": "2018-06-24T05:00:00Z",
					"end": "2018-06-24T05:45:00Z"
				},
				"stops": [{
					"id": 471958,
					"university_id": 1,
					"bus_service_id": 100221,
					"stop_id": 1,
					"arrival": "2018-06-24T05:00:00Z",
					"departure": "2018-06-24T05:00:00Z"
				}, {
					"id": 471959,
					"university_id": 1,
					"bus_service_id": 100221,
					"stop_id": 2,
					"arrival": "2018-06-24T05:25:00Z",
					"departure": "2018-06-24T05:25:00Z"
				}, {
					"id": 471960,
					"university_id": 1,
					"bus_service_id": 100221,
					"stop_id": 3,
					"arrival": "2018-06-24T05:45:00Z",
					"departure": "2018-06-24T05:45:00Z"
				}]
			},
			"departure_stop_id": 1,
			"destination_stop_id": 3
		}],
		"journey_home": [{
			"service": {
				"service": {
					"id": 100225,
					"university_id": 1,
					"name": "Route A",
					"start_stop_id": 1,
					"end_stop_id": 3,
					"start": "2018-06-24T09:00:00Z",
					"end": "2018-06-24T09:45:00Z"
				},
				"stops": [{
					"id": 471970,
					"university_id": 1,
					"bus_service_id": 100225,
					"stop_id": 1,
					"arrival": "2018-06-24T09:00:00Z",
					"departure": "2018-06-24T09:00:00Z"
				}, {
					"id": 471971,
					"university_id": 1,
					"bus_service_id": 100225,
					"stop_id": 2,
					"arrival": "2018-06-24T09:25:00Z",
					"departure": "2018-06-24T09:25:00Z"
				}, {
					"id": 471972,
					"university_id": 1,
					"bus_service_id": 100225,
					"stop_id": 3,
					"arrival": "2018-06-24T09:45:00Z",
					"departure": "2018-06-24T09:45:00Z"
				}]
			},
			"departure_stop_id": 3,
			"destination_stop_id": 1
		}]
	}
}
```
