---
layout: page
---

# Tutorial: Get plants by a property

In this tutorial, you learn how to get a list of plants with the same property value. This requires you to perform a get (`GET`) request on the [`plant`](../api/plant) resources in the service. You can query plants by the following properties:

* `id`
* `name`
* `species`
* `date_planted`
* `location`

**Note:** For more information on these properties, see the [plant](../plant) resource page.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Make sure your development system is set up to work with the Plant Buddy service. See the [Quickstart](../api/quickstart) topic for more information.

## Get plants by a property

**Note:** The following instructions use the `location` property as an example. You can use the same instructions to query plants by the other eligible properties.

1. Make sure your local service is running. If it's not running, start it by using this command:

    ```shell
    cd <your-github-workspace>/plant-buddy-service/api
    json-server -w plant-carelog-db-source.json
    ```

1. Open the Postman app on your desktop.
1. Create a new request with these values:
    * **METHOD**: GET
    * **URL**: `{{base_url}}/plants?location=<replace this text with the location value>`
   
   **Example:**

   `http://localhost:3000/plants?location=Kitchen`
   
      **Note:** Title values are case sensitive.


1. In the Postman app, select **Send** to make the request.
1. Watch for the response body, which should look something like the following:

    ```js
   [
    {
        "id": 2,
         "name": "Aloe Vera",
         "species": "Aloe barbadensis miller",
         "date_planted": "2021-08-20",
         "location": "Kitchen",
         "notes": "Water sparingly; prefers bright light."
    },
    {
        "id": 3,
        "name": "Snake Plant",
        "species": "Sansevieria trifasciata",
        "date_planted": "2020-11-05",
        "location": "Kitchen",
        "notes": "Very hardy, tolerates low light."
    }
   ]
    ```
  
   If there are locations matching the entered search value, an empty array is returned.

For more tutorials on the `plant` resource, see the following:

* [Create a plant](tutorials/create-a-plant.md)
* [Update a plant property](tutorials/update-plant-property.md)