---
layout: page
---

# Update a carelog property

The Patch request updates a specified property but does not change the other properties in the [`carelog`](carelog) object. When a carelog is created, a unique identifier (ID) is assigned to it. When updating a carelog property, you need to provide the carelog `id` in the REST URL.

## URL

```console
{server_url}/carelogs/{id}
```

## Method

PATCH


## Properties

This table lists the carelog properties that can be updated.

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `plant_id` | Number | The plant's unique record ID. |
| `care_type` | String | Type of care given to a plant (e.g. "Watering"). |
| `date` | String | Date the care was given. |
| `notes` | String | Any notes that the user might want to add about the care given (e.g. "Watered thoroughly until water drained from the bottom"). |


## Request headers

None.

## Sample request body

This example updates the carelog's `care_type` value. The other properties are not changed.

```json
    {
      "care_type": "Updated care type"
    }
```

## cURL request example

```cURL
curl --location --request PATCH 'localhost:3000/users/3' \
--header 'Content-Type: application/json' \
--data-raw '    {
        "care_type": "Updated care type"
    }'
```

## Sample return body

The return shows the carelog record with the updated `care_type` value.

```json
    {
      "id": 1,
      "plant_id": 1,
      "care_type": "Updated care type",
      "date": "2024-05-20",
      "notes": "Watered thoroughly until water drained from the bottom."
    }
```


## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Updates the carelog property and returns the carelog record with the updated property value. |
| 404 | Error | Specified carelog record not found. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
