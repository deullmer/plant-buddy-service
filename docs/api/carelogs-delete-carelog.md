# Delete a carelog by ID

Deletes the carelog specified by the `id` parameter from the [`carelog`](carelog.md) resource, if the carelog exists.

## URL

```shell

{server_url}/carelogs/{id}
```

## Params

| Parameter name | Type | Description |
| -------------- | ------ | ------------ |
| `id` | number | The record ID of the carelog to delete. |

## Request headers

Content-Type: application/json

## Request body

DELETE {server_url}/carelogs/{id}

## Return body

Returns the carelog you deleted from the carelog resource.

```js
[
    {
        "id": 4,
        "plant_id": 1,
        "care_type": "Misting",
        "date": "2024-05-05",
        "notes": "Misted leaves to increase humidity."
    }
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Action completed successfully |
| 202 | Accepted| Action has been queued |
| 204 | No Content| Action has been performed, but the response does not include an entity |
| 404 | Error | Specified user record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related topics

[Delete a plant](plants-delete-plant.md)

