---
layout: page
---
# `plant` resource

Base endpoint:

```shell
{server_url}/plants
```

Contains information about the plants that have been added to the service.

## Resource properties

Sample `plant` resource:

```js
{

  "name": "Snake Plant",
  "species": "Sansevieria trifasciata",
  "date_planted": "2020-11-05",
  "location": "Bedroom",
  "notes": "Very hardy, tolerates low light.",
  "id": 3
}
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `name` | string | Name of the plant. |
| `species` | string | Species of the plant. |
| `date_planted` | string | Date on which the plant was planted. |
| `location` | string | Location of the plant (e.g. "Living room"). |
| `notes` | string | Notes about the plant's condition and/or characteristics (e.g. "Very hardy, tolerates low light"). |
| `id` | integer | The plant's unique record ID. |

## Operations

The `plant` resource supports these operations.

### Create (POST)

* [Create a plant](plants-create-plant.md)

### READ (GET)

* [Get all plants](plants-get-all-plants.md)

### UPDATE (PATCH)

* [Update a plant property](plants-update-plant-property.md)

### DELETE

* [Delete a plant](plants-delete-plant.md)

## See also

* [carelog resource](carelog.md)
