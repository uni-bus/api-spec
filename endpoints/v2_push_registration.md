# Uni Bus API Endpoints

## Usage

Please [see the README for more information](../README.md) about using this API.

## Common API Parameters

Please [see this document](v2_common.md) for Common Parameters required as part of the request.

## Push Registration

**POST** `/v2/{university}/push`

Returns information about the next departures from a given Bus Stop.

Request:

```json
{  
  "device_id": "00000000-0000-0000-0000-000000000000",
  "device_name": "iPhone X",
  "device_type": "iPhone",
  "platform": "iOS",
  "os_version": "12.0.0",
  "application_version": "1.2.3",
  "token": "abcdef000abcdef000abcdef000abcdef000abcdef"
}
```

* `device_id` - (Required) The UUID of the current device - [more information is available about this identifier here](https://unibus.co/privacy.html).

* `device_name` - (Required) The name of the current device, such as `iPhone X`.

* `device_type` - (Required) The type of the device, such as `iPhone` or `iPad`.

* `platform` - (Required) The platform of the device, such as `iOS` or `Android`.

* `os_version` - (Required) The version of the Operating System installed on the device.

* `application_version` - (Required) The version of the Uni Bus Application.

* `token` - (Required) The Push Notification Token obtained from Apple or Google Play.

Response:

* `HTTP 201` when successful
* `HTTP 400` when data is missing
* `HTTP 500` when an internal server error happens
