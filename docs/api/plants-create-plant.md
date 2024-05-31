---
layout: page
---

# Create a plant

Creates a new [`plant`](plant) for a user of the Plant Buddy service.
The request body contains the new plant details that are derived from the plant properties, which you must specify.

## URL

```shell

{POST}{server_url}/plants/
```

## Request headers

This request does not use any authorization. The endpoint is available to all users and applications.

No headers required.

## Request body

In the request body, specify a JSON representation of the [`plant`](plant) object. The following table lists the properties that are required when you create a plant.

| Property | Description | Type | Required | Notes |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| `name` | Name of the plant | string | Required | |
| `species` | Species of the plant. | string | Required | |
| `date_planted` | Date on which the plant was planted. | string | Required | |
| `location` | Location of the plant. | string | Required | |
| `notes` | Notes about the plant's condition and/or characteristics (e.g. "Very hardy, tolerates low light"). | string | Optional | |


## Sample request

The POST body should look something like this. You can change the values of each property as you would like.

```js
[
    {
      "name": "Snake Plant",
      "species": "Sansevieria trifasciata",
      "date_planted": "2020-11-05",
      "location": "Bedroom",
      "notes": "Very hardy, tolerates low light."
    }
]
```

## Response body
The following example shows the response. Note that the plant name should be the same as you used in your **Request body**, and the response should include the new plant's `id`, which is automatically generated when the plant is created.

```js
[
    {
      "name": "Snake Plant",
      "species": "Sansevieria trifasciata",
      "date_planted": "2020-11-05",
      "location": "Bedroom",
      "notes": "Very hardy, tolerates low light."
      "id": 2
    }
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 201 | Created | Plant data created successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |