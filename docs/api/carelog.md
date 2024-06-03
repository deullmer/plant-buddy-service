---
layout: page
---
# `carelog` resource

Base endpoint:

```shell
{server_url}/carelogs
```

Contains the carelogs that have been added to the service. Carelogs provide details on the care given to plants over time.

**Note:** A plant must be added to the service before a carelog can be created for it.

## Resource properties

Sample `carelog` resource:

```js

{
      "id": 1,
      "plant_id": 1,
      "care_type": "Watering",
      "date": "2024-05-20",
      "notes": "Watered thoroughly until water drained from the bottom."
}
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `plant_id` | Number | The plant's unique record ID. |
| `care_type` | String | Type of care given to a plant (e.g. "Watering"). |
| `date` | String | Date the care was given. |
| `notes` | String | Any notes that the user might want to add about the care given (e.g. "Watered thoroughly until water drained from the bottom"). |
| `id` | Number | The carelog's unique record ID. |

## Operations

The `carelog` resource supports these operations.

### Create (POST)

* [Create a carelog](carelogs-create-carelog.md)

### READ (GET)

* [Get all carelogs](carelogs-get-all-carelogs.md)

### UPDATE (PATCH)

* [Update a carelog property](carelogs-update-carelog-property.md)

### DELETE

* [Delete a carelog](carelogs-delete-carelog.md)

## See also

* [plant resource](plant.md)