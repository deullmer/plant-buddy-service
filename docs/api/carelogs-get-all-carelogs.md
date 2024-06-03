---
layout: page
---
# Get all carelogs

Returns an array of [`carelog`](carelog.md) objects containing all the carelogs that have been created within the service.

## URL

```shell

{server_url}/carelogs
```

## Params

None

## Request headers

None

## Request body

None

## Return body

```js
[
    {
        "id": 1,
        "plant_id": 1,
        "care_type": "Watering",
        "date": "2024-05-20",
        "notes": "Watered thoroughly until water drained from the bottom."
    },
    {
        "id": 2,
        "plant_id": 2,
        "care_type": "Fertilizing",
        "date": "2024-05-15",
        "notes": "Added half-strength liquid fertilizer."
    }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
