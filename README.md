![Procedural Generation](http://i.imgur.com/J4OqZye.png)

# Procedural Generation

Procedural generation is when you use a computer to semi-randomly create content. In games it can be used to create environments, enemy placements, and treasure. And it can be used to create simulations of experiments where it would be too costly or dangerous to make the experiment.


## Randomness

When generating content randomly you don't really want the end product to be truely random. You really want it to be psudo-random, random with just enough structure for it to make sense.


## Teleological vs. Ontogenetic

There are two approaches to procedural generation and they are: Teleological and Ontogenetic.

Teleological is the approach where you create an accurate physical model of the environment and the process that govern it, then you run the simulation and observe the results.
Ontogenetic is the approach where you observe the end result and then attempt to reproduce the result with algorithms.
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

![Diamond-Square Algorithm](https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/Plasmafractal.gif/200px-Plasmafractal.gif)

L-System

![L-System](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5d/Graftal7.png/150px-Graftal7.png)

Perlin Noise

![Perlin Noise](https://upload.wikimedia.org/wikipedia/commons/d/da/Perlin_noise.jpg)

## Additional Resources

-   [Procedural Content Generation Wiki](http://pcg.wikidot.com/)
-   [Amit’s Game Programming Information](http://www-cs-students.stanford.edu/~amitp/gameprog.html)
-   [An Introduction to Creating a Tile Map Engine](http://gamedevelopment.tutsplus.com/tutorials/an-introduction-to-creating-a-tile-map-engine--gamedev-10900)
-   [Create a Procedurally Generated Dungeon Cave System](http://gamedevelopment.tutsplus.com/tutorials/create-a-procedurally-generated-dungeon-cave-system--gamedev-10099)
-   [Procedural Level Generation in Games Tutorial: Part 1](https://www.raywenderlich.com/49502/procedural-level-generation-in-games-tutorial-part-1)
-   [Khan Academy](https://www.khanacademy.org/computing/computer-programming/programming-natural-simulations/programming-randomness/a/random-walks)
-   [Perlin Noise Code - Banksean](https://gist.github.com/banksean/304522)
-   [Perlin Noise Code wwwtyro](https://github.com/wwwtyro/perlin.js/blob/master/perlin.js)
-   [ExtraCredits - Procedural Content - Youtube](https://www.youtube.com/watch?v=TgbuWfGeG2o)
-   [Sebastian Lague - Procedural Landmass Generation - Youtube](https://www.youtube.com/watch?v=wbpMiKiSKm8)




## [License](LICENSE)

Source code distributed under the MIT license. Text and other assets copyright
General Assembly, Inc., all rights reserved.
