---
layout: page
---

# Create a carelog

Creates a new [`carelog`](carelog) for a plant registered in the Plant Buddy service.
The request body contains the new carelog details that are derived from the carelog properties, which you must specify.

## URL

```shell

{POST}{server_url}/carelogs/
```

## Request headers

This request does not use any authorization. The endpoint is available to all users and applications.

No headers required.

## Request body

In the request body, specify a JSON representation of the [`carelog`](carelog) object. The following table lists the properties that are required when you create a carelog.

| Property | Description | Type | Required | Notes |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| `plant_id` | string | ID of the plant that is attached to the carelog. | Required | |
| `care_type` | string | Type of care given to the plant (e.g. "Watering"). | Required | |
| `date` | Date the care was given. | string | Required | |
| `notes` | string | Any notes that the user might want to add about the care given (e.g. "Watered thoroughly until water drained from the bottom"). | Required | |


## Sample request

The POST body should look something like this. You can change the values of each property as you would like.

```js
[
    {
      "plant_id": 1,
      "care_type": "Misting",
      "date": "2024-05-05",
      "notes": "Misted leaves to increase humidity."
    }
]
```

## Response body

The following example shows the response. Note that the returned properties should match what you entered in your **Request body**, and the response should include the new carelog's `id`, which is automatically generated when the carelog is created.

```js
[
    {
      "plant_id": 1,
      "care_type": "Misting",
      "date": "2024-05-05",
      "notes": "Misted leaves to increase humidity.",
      "id": 2
    }
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 201 | Created | Carelog data created successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |