---
layout: page
---

# Update a carelog property

In this tutorial, you'll learn how to use Postman to update a carelog property. The following table lists the carelog properties that can be updated:

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `plant_id` | Number | The ID of the plant that the carelog is attached to. |
| `care_type` | String | Type of care given to a plant (e.g. "Watering"). |
| `date` | String | Date the care was given. |
| `notes` | String | Any notes that the user might want to add about the care given (e.g. "Watered thoroughly until water drained from the bottom"). |

This tutorial takes about 15 minutes to complete.

## Before you begin

Before you start working with Plant Buddy, you need to make sure that you have the prerequisite tools, and then you need to set up your development system to work with the Plant Buddy service. For instructions, see the [Quickstart](tutorials/quickstart.md) guide.

## Get a list of carelogs

**Note:** If you know the ID of the carelog that you want to update, you can skip this section.

If you don't know the ID of the carelog that you want to update, run a GET request to list all the carelogs in the Plant Buddy service's database so you can find the ID.

To get a list of carelogs:

1. Make sure your local service is running. If it's not running, start it by running the following commands:

    ```shell
    cd <your-github-workspace>/plant-buddy-service/api
    json-server -w plant-buddy-db-source.json
    ```

1. In Postman, add a new request with these values:

    * **METHOD** — `GET`
    * **URL** — `http://localhost:3000/carelogs`
    * **Headers** — `Content-Type: application/json`
    * **Request body** — None

1. In Postman, click **Send**.

   The Plant Buddy service returns a JSON object containing all the carelogs you have recorded. Each carelog has the following format. Note the `id` of the carelog that you want to update.

  ```json
    {
      "id": 1,
      "plant_id": 1,
      "care_type": "Watering",
      "date": "2024-05-20",
      "notes": "Watered thoroughly until water drained from the bottom."
    }
```

## Update the carelog property

Once you know the carelog `id`, send a `PATCH` request to the `/carelogs/{id}` endpoint to update the property that you want to change.

To update a carelog property:

1. Make sure your local service is running. If it's not running, start it by running the following commands:

    ```shell
    cd <your-github-workspace>/plant-buddy-service/api
    json-server -w plant-carelog-db-source.json
    ```

1. In Postman, add a new request with these values:
    * **METHOD** — `PATCH`
    * **URL** — `http://localhost:3000/plants/{id}`
    * **Headers** — `Content-Type: application/json`

1. In the **Request Body**, add only the updated description of the property that you want to change. The following example uses the `care_type` property:

    ```json
    {
    "care_type": "<updated care type>"
    }
    ```

1. Click **Send**.

   The Plant Buddy service updates the carelog and returns a `200 OK` along with the updated carelog as a JSON object.  

## Next steps

After doing this tutorial in Postman, you might like to repeat it in your favorite programming language. To do this, adapt the values from the tutorial to the properties and arguments that the language uses to make REST API calls.

## Related topics

* [Plant resource](../api/plant.md)
* [Carelog resource](../api/carelog.md)
