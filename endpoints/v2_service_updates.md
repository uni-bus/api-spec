# Uni Bus API Endpoints

## Usage

Please [see the README for more information](../README.md) about using this API.

## Common API Parameters

Please [see this document](v2_common.md) for Common Parameters required as part of the request.

## Service Updates

**GET** `/v2/{university}/updates`

This endpoint returns a list of known issues with the Bus Service.

If there are no Service Updates, an empty array is returned as shown:

```json
{
  "service_updates": []
}
```

Otherwise the Service Updates are returned as shown below:

```json
{
  "service_updates": [
    {
      "id": 7,
      "title": "Delays on the S5",
      "body": "Delays of up to 20 minutes expected on the S5 at Hauptbahnhof due to a broken down freight train",
      "posted_by": "Tom H",
      "publish_date": "2018-06-15T15:50:36Z",
      "last_modified": "2018-06-15T15:50:36Z"
    }
  ]
}
```
