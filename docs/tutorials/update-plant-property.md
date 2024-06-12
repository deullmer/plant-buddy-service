---
layout: page
---

# Update a plant property

In this tutorial, you'll learn how to use Postman to update a plant property. Updatable plant properties include `name`, `species`, `date_planted`, `location`, and `notes`.

This tutorial takes about 15 minutes to complete.

## Before you begin

Before you start working with Plant Buddy, you need to make sure that you have the prerequisite tools, and then you need to set up your development system to work with the Plant Buddy service. For instructions, see the [Quickstart](tutorials/quickstart.md) guide.

## Get a list of plants

**Note:** If you know the ID of the plant that you want to update, you can skip this section.

If you don't know the ID of the plant that you want to update, run a GET request to list all the plants in the Plant Buddy service's database so you can find the ID.

To get a list of plants

1. Make sure your local service is running. If it's not running, start it by running the following commands:

    ```shell
    cd <your-github-workspace>/plant-buddy-service/api
    json-server -w plant-buddy-db-source.json
    ```

1. In Postman, add a new request with these values:

    * **METHOD** — `GET`
    * **URL** — `http://localhost:3000/plants`
    * **Headers** — `Content-Type: application/json`
    * **Request body** — None

1. In Postman, click **Send**.

   The Plant Buddy service returns a JSON object containing all the plants you have recorded. Each plant has the following format. Note the `id` of the plant that you want to update.

    ```json
   {
      "id": 2,
      "name": "Aloe Vera",
      "species": "Aloe barbadensis miller",
      "date_planted": "2021-08-20",
      "location": "Kitchen",
      "notes": "Water sparingly; prefers bright light."
    }
    ```

## Update the plant property

Once you know the plant `id`, send a `PATCH` request to the `/plants/{id}` endpoint to update the property that you want to change.

### To update the plant description

1. Make sure your local service is running. If it's not running, start it by running the following commands:

    ```shell
    cd <your-github-workspace>/plant-buddy-service/api
    json-server -w plant-carelog-db-source.json
    ```

1. In Postman, add a new request with these values:
    * **METHOD** — `PATCH`
    * **URL** — `http://localhost:3000/plants/{id}`
    * **Headers** — `Content-Type: application/json`

1. In the **Request Body**, add only the updated description of the property that you want to change. The following example uses the `location` property:

    ```json
    {
    "location": "Updated location"
    }
    ```

1. Click **Send**.

   The Plant Buddy service updates the plant description and returns a `200 OK` along with the updated plant as a JSON object.  

## Next steps

After doing this tutorial in Postman, you might like to repeat it in your favorite programming language. To do this, adapt the values from the tutorial to the properties and arguments that the language uses to make REST API calls.

## Related topics

* [Plant resource](../api/plant.md)
* [Carelog resource](../api/carelog.md)
