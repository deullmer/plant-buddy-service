---
layout: page
---

# Update a plant property

The Patch request updates a specified property but does not change the other properties in the [`plant`](plant) object. When a plant is created, a unique identifier (ID) is assigned to it. When updating a plant property, you need to provide the plant `id` in the REST URL.

## URL

```console
{server_url}/plants/{id}
```

## Method

PATCH


## Properties

This table lists the plant properties that can be updated.

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `name` | string | Name of the plant. |
| `species` | string | Species of the plant. |
| `date_planted` | string | Date on which the plant was planted. |
| `location` | string | Location of the plant (e.g. "Living room"). |
| `notes` | string | Notes about the plant's condition and/or characteristics (e.g. "Very hardy, tolerates low light"). |


## Request headers

None.

## Sample request body

This example updates the plant's `location` value. The other properties are not changed.

```json
    {
      "location": "Updated location"
    }
```

## cURL request example

```cURL
curl --location --request PATCH 'localhost:3000/users/3' \
--header 'Content-Type: application/json' \
--data-raw '    {
        "location": "Updated location"
    }'
```

## Sample return body

The return shows the plant record with the updated `location` value.

```json
    {
        "id": 2,
        "name": "Aloe Vera",
        "species": "Aloe barbadensis miller",
        "date_planted": "2021-08-20",
        "location": "Updated location",
        "notes": "Water sparingly; prefers bright light."
    }
```


## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Updates the plant property and returns the plant record with the updated property value. |
| 404 | Error | Specified plant record not found. |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
