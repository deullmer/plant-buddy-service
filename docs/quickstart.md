---
layout: page
---

# Quickstart

In this quickstart, you’ll learn about:

* The prerequisite tools that you need to work with Plant Buddy API.
* The steps you must complete to make sure your development system is set up to work with the Plant Buddy API.

This quickstart is specific to the Windows operating system and takes about 20 minutes to complete.

## Prerequisite tools

To work with the Plant Buddy API, you need the following:

* A [GitHub account](https://github.com)
* A Windows computer running a current or long-term support (LTS version of the operating system).
* The following software on your development system:
  * [Git](https://docs.github.com/en/get-started/quickstart/set-up-git) (for the command line)
  * [GitHub Desktop](https://desktop.github.com) (optional)
  * A fork of the [Plant Buddy service repo](https://github.com/deullmer/plant-buddy-service)
  * A current/LTS version of [node.js](https://nodejs.org/en/)
  * A current version of [json-server](https://www.npmjs.com/package/json-server)
  * A current copy of the database file. You can get this by syncing your fork.
  * **TIP**: If you're using a fork of the repo, create a working branch in which to perform your work. Create a new branch for each tutorial to prevent a mistake in one from affecting your work in another.
  * The [Postman desktop app](https://www.postman.com/downloads/). Because you run the **Plant Buddy service** on your development system with an `http://localhost` hostname, the web-version of Postman can't perform the exercises.

## Test your development system

To test your development system, follow these steps:

1. Create and checkout a test branch of your fork of the Plant Buddy service repo. Your `GitHub repo workspace` is the directory that contains your fork of the `plant-buddy-service` repo.

    ```shell
    cd <your GitHub repo workspace>
    ls
    # (see the plant-buddy-service directory in the list)
    cd plant-buddy-service
    git checkout -b tutorial-test
    cd api
    json-server -w plant-carelog-db-source.json
    ```
    
    If your development system is installed correctly, the service should start and display the URL of the service: `http://localhost:3000`.

1. Make a test call to the service.

    ```shell
    curl http://localhost:3000/plants
    ```

    If the service is running correctly, you should see a list of plants from the service, such as in this example.

    ```json
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
      },
      ...
    ]
    ```

    If you don't see a list of plants, or receive an error in any step
of the procedure, investigate and correct the error before continuing.
Some common situations that cause errors include:

    1. A mistyped command.
    1. Not being in the correct directory.
    1. A required software component isn't installed correctly.
    1. A required software component is out of date.

    If you see the list of plants from the service, you're ready to work with Plant Buddy. The following tutorials cover some common developer tasks to help you get started:

    * [Get plants by a property](tutorials/get-plants-by-property.md)
    * [Update a plant property](tutorials/update-plant-property.md)
