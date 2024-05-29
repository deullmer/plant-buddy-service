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
      "id": 3,
      "name": "Snake Plant",
      "species": "Sansevieria trifasciata",
      "date_planted": "2020-11-05",
      "location": "Bedroom",
      "notes": "Very hardy, tolerates low light."
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

### Add (POST)

* [Add a plant](plants-add-plant)

### READ (GET)

* [Get all plants](plants-get-all-plants)
* [Get a plant by ID](plants-get-plant-by-id)
* [Get plants by species](plants-get-plant-by-species)
* [Get plants by date planted](plants-get-plants-by-date-planted)
* [Get plants by location](plants-get-plants-by-location)

### UPDATE (PATCH)

* [Change a plant property](plants-change-plant-property)

### DELETE

* [Delete plant by ID](plants-delete-plant-by-id)