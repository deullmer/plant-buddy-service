# Delete a plant by ID

Deletes the plant specified by the `id` parameter from the [`plant`](plant) resource, if the plant exists.

## URL

```shell

{server_url}/plants/{id}
```

## Params

| Parameter name | Type | Description |
| -------------- | ------ | ------------ |
| `id` | number | The record ID of the plant to delete. |

## Request headers

Content-Type: application/json

## Request body

DELETE {server_url}/plants/{id}

## Return body

Returns the plant you deleted from the plant resource.

```js
[
    {
        "id": 4,
        "name": "Peace Lily",
        "species": "Spathiphyllum wallisii",
        "date_planted": "2023-02-10",
        "location": "Office",
        "notes": "Prefers low light and high humidity. Keep soil consistently moist."
    }
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Action completed successfully. |
| 202 | Accepted| Action has been queued. |
| 204 | No Content| Action has been performed, but the response does not include an entity. |
| 404 | Error | Specified plant record not found. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related topics

[Delete a carelog](carelogs-delete-carelog.md)

