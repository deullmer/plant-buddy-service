---
layout: page
---
# Get all plants

Returns an array of [`plant`](plant.md) objects containing all the plants that have been created within the service.

## URL

```shell

{server_url}/plants
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
        "name": "Fern",
        "species": "Nephrolepis exaltata",
        "date_planted": "2022-03-15",
        "location": "Living Room",
        "notes": "Loves humidity and indirect light."
    },
    {
        "id": 2,
        "name": "Aloe Vera",
        "species": "Aloe barbadensis miller",
        "date_planted": "2021-08-20",
        "location": "Kitchen",
        "notes": "Water sparingly; prefers bright light."
    }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
