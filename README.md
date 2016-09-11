[![Procedural Generation](http://i.imgur.com/J4OqZye.png)]

# Procedural Generation

Procedural generation is when you use a computer to semi-randomly create content. In games it can be used to create environments, enemy placements, and treasure. And it can be used to create simulations of experiments where it would be too costly or dangerous to make the experiment.


## Randomness

When generating content randomly you don't really want the end product to be truely random. You really want it to be psudo-random, random with just enough structure for it to make sense.


## Teleological vs. Ontogenetic

There are two approaches to procedural generation and they are: Teleological and Ontogenetic.

Teleological is the approach where you careate an accurate physical model of the environment and the process that govern it, then you run the simulation and observe the results.
Ontogenetic is the approach where you observe the end result and then attemp to reproduce the result with algorithms.
For example: To create a mountain I would create create continents and tectonic movement and see where the mountains would appear, vs creating or using an algorithm to make a mountain appear.

Examples of Teleological Algorithms:

-   Artificial Life
-   Dynamic Weather
-   Fire Propagation
-   Fluid Dynamics
-   Genetic Algorithm
-   Rain Drop Algorithm
-   Reaction-Diffusion System (Chemestry)

Examples of Ontogenetic Algorithms:

-   Diamond-Square Algorithm: Generating heightmaps
-   L-System: Plant generation
-   Mazes
-   Perlin Noise: Adds layers of noises. Higher noises are more precise, but are less weighted.
-   Simplex Noise: A redesign of Perlin Noise, by Ken Perlin.
-   Voronoi Diagram: organic looking division rather than rectangular or circular systems.

Visuals:
Diamond-Square Algorithm

[![Diamond-Square Algorithm](https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/Plasmafractal.gif/200px-Plasmafractal.gif)]

L-System

[![L-System](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5d/Graftal7.png/150px-Graftal7.png)]

Perlin Noise

[![Perlin Noise](https://upload.wikimedia.org/wikipedia/commons/d/da/Perlin_noise.jpg)]




| Response method      | What it means                                                                         |
|:---------------------|:--------------------------------------------------------------------------------------|
| `res.end()`          | End the response process.                                                             |
| `res.json(jsObject)` | Send a JSON response.                                                                 |
| `res.redirect()`     | Redirect a request.                                                                   |
| `res.sendStatus()`   | Set the response status code and send its string representation as the response body. |

## Annotate Along: Summarize Actions in Examples Controller

Let's practice reading unfamiliar code by annotating
[`app/controllers/examples.js`](app/controllers/examples.js). As we read each
controller action, keep the following questions in mind.

-   What is the purpose of this action?
-   Does it need a singular or plural resource to build its response?
-   How is the action handling errors?
-   Why do we need to check for the existence of a record after querying?
-   Where do we get IDs from?
-   Where do we get data from when creating or updating a record?
-   Which terminal handler is used to send a response?

## Demo: An Example Express Model

Let's read [`app/models/example.js`](app/models/example.js) and answer the
following questions together:

-   What library are we using to model our resources? Does it have anything to
    do with Express?
-   What does the underscore denote in `_owner`?
-   Where should we go to find out more about an owner?
-   Why aren't we using an arrow function for the virtual attribute `length`?

## Lab: Create an Example

Start the server and try creating an example by issuing a `POST /examples`. What
happens? You might find some help in the [`scripts`](scripts) directory.

When you've created an example, try using its ID to request it via `GET
/examples/:id`. Then, create another and check your work with `GET /examples`.

## Code-Along: `POST /books`

Only authenticated users should be able to create a book.

Let's create our book model together, and one controller action. Don't forget
a route!

Make sure to save a reference to the user that created the book so we can user
it later to check ownership.

We'll need to write a test script to check our work. We'll save it as
[`scripts/books-create.sh`](scripts/books-create.sh).

We're done when we see a response similar to this one:

Expected response:

```sh
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: application/json; charset=utf-8

{
  "book": {
    "__v": 0,
    "updatedAt": "2016-03-09T03:23:58.000Z",
    "createdAt": "2016-03-09T03:23:58.000Z",
    "_owner": "56df9716c19957cb0d836c4a",
    "title": "Invisible Monsters",
    "author": "Chuck Palahniuk",
    "price": 10.99,
    "_id": "56df974ec19957cb0d836c4d"
  }
}
```

## Code-Along: `GET /books`

Visitors to the client web application should be able to see all the books
without being logged in.

We will need to write a controller action and a test script.

Expected response:

```sh
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: application/json; charset=utf-8

{
  "books": [
    {
      "_id": "56df974ec19957cb0d836c4c",
      "updatedAt": "2016-03-09T03:23:58.000Z",
      "createdAt": "2016-03-09T03:23:58.000Z",
      "_owner": "56df9716c19957cb0d836c4a",
      "title": "Between the World and Me",
      "author": "Ta-Nehisi Coates",
      "price": 12.99,
      "__v": 0
    },
    {
      "_id": "56df974ec19957cb0d836c4d",
      "updatedAt": "2016-03-09T03:23:58.000Z",
      "createdAt": "2016-03-09T03:23:58.000Z",
      "_owner": "56df9716c19957cb0d836c4a",
      "title": "Invisible Monsters",
      "author": "Chuck Palahniuk",
      "price": 10.99,
      "__v": 0
    }
  ]
}
```

## Lab: `GET /books/:id`

Visitors to the client web application should be able to see any book without
being logged in.

You will need to write a controller action and a test script.

Expected response:

```sh
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: application/json; charset=utf-8

{
  "book": {
    "_id": "56df974ec19957cb0d836c4c",
    "updatedAt": "2016-03-09T03:23:58.000Z",
    "createdAt": "2016-03-09T03:23:58.000Z",
    "_owner": "56df9716c19957cb0d836c4a",
    "title": "Between the World and Me",
    "author": "Ta-Nehisi Coates",
    "price": 12.99,
    "__v": 0
  }
}
```

## Lab: `PATCH /books/:id`

Only authenticated users should be able to change a book. They should not be
able to change other users' books.

You will need to write a controller action and a test script.

Expected response:

```sh
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: application/json; charset=utf-8
```

You may wish to retrieve the book you changed to check your work.

If a different user than the owner tries to make the change, you should instead
see:

```sh
HTTP/1.1 404 Not Found
X-Powered-By: Express
Content-Type: application/json; charset=utf-8

{
  "error": {
    "message": "Not Found",
    "error": {
      "status": 404
    }
  }
}
```

## Lab: `DELETE /books/:id`

Only authenticated users should be able to delete a book. They should not be
able to delete other users' books.

You will need to write a controller action and a test script.

Expected response:

```sh
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: application/json; charset=utf-8
```

If a different user than the owner tries to make the change, you should instead
see:

```sh
HTTP/1.1 404 Not Found
X-Powered-By: Express
Content-Type: application/json; charset=utf-8

{
  "error": {
    "message": "Not Found",
    "error": {
      "status": 404
    }
  }
}
```

## Additional Resources

-   [Express - Node.js web application framework](http://expressjs.com/)
-   [ga-wdi-boston/express-template: Railsified express server](https://github.com/ga-wdi-boston/express-template)

## [License](LICENSE)

Source code distributed under the MIT license. Text and other assets copyright
General Assembly, Inc., all rights reserved.
