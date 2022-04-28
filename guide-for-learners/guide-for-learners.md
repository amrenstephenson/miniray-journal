# A Guide to Learning Ray-Based Rendering

## Why should I bother learning about it?

![Image of two ray traced spheres in a box.](https://upload.wikimedia.org/wikipedia/commons/0/0e/Box_-_Path_Tracing_High.png)

<span style="opacity: 0.7"><a href="https://commons.wikimedia.org/wiki/File:Box_-_Path_Tracing_High.png">ThKa (Thomas Kabir)</a>, <a href="https://creativecommons.org/licenses/by-sa/2.0/de/deed.en">CC BY-SA 2.0 DE</a>, via Wikimedia Commons</span>

Firstly, because the results can be stunningly lifelike and beautiful. I remember seeing [this demo](https://youtu.be/hTf1otkzTz4) (an absolute must-watch) for the first time and being taken back by how realistic it looked. My brain could not decipher the difference between reality and artistry. I would argue that this is a sufficient reason alone to pursue this, simply because there is an immense joy in creating extremely detailed simulations, often with staggeringly little code.

Secondly, graphics are all too often left to third-party [libraries](<https://en.wikipedia.org/wiki/Library_(computing)>) or [game engines](https://en.wikipedia.org/wiki/Game_engine), without developers truly understanding what's going on under the hood. This was a key reason for my desire to learn about ray tracing, because while I have developed a lot of games, I had never written any [3D rendering](https://en.wikipedia.org/wiki/3D_rendering) code myself. Additionally, it starts to give you an idea of the clever optimisations that developers have used, along with an appreciation for why [GPUs](https://en.wikipedia.org/wiki/Graphics_processing_unit) are needed.

Lastly, ray tracing provides an ideal project for those wishing to try their hand at coming up with their own implementations to classic problems. The majority of the mathematical concepts involved can be understood after brief explanations (see the resources section below), and simple solutions often work well. Additionally, if you do get stuck, there are plenty of complete code examples available online (some of these are listed later).

## Who is this guide really for?

![Black and white image of a silhouette in a tunnel.](https://upload.wikimedia.org/wikipedia/commons/f/f7/The_Photographer.jpg)

<span style="opacity: 0.7"><a href="https://commons.wikimedia.org/wiki/File:The_Photographer.jpg">Joaquim Alves Gaspar</a>, <a href="http://creativecommons.org/licenses/by-sa/3.0/">CC BY-SA 3.0</a>, via Wikimedia Commons</span>

This guide is aimed at anyone interested in coding a [ray tracing](<https://en.wikipedia.org/wiki/Ray_tracing_(graphics)>) engine from a beginner ("I have no idea what ray tracing even is") perspective. It is geared towards allowing you to explore key concepts on your own, and I've tried to avoid giving spoon-fed solutions. The idea is that you can read around the subject before coming up with your own unique solution.

The main prerequisite is proficiency in a programming language of your choice. I used [JavaScript](https://en.wikipedia.org/wiki/JavaScript), so a lot of the resources in this guide refer to JavaScript, but the principles are the same in any [high-level language](https://en.wikipedia.org/wiki/High-level_programming_language). This project is not suitable for people who have only just started learning to code, and is much better suited to those who have completed several projects in their chosen language. However, if you are interested in starting to learn a programming language, there are some very good YouTube videos on the subject which offer a great starting point:

- [Learn JavaScript - Full Course for Beginners](https://youtu.be/PkZNo7MFNFg)
  This 134-part course goes through all of the basics of JavaScript at a nice steady pace that I think is ideal for new learners. However, if you have coded in other languages before, then you will likely find this course a bit tedious.
- [Python Tutorial - Python Full Course for Beginners](https://youtu.be/_uQrJ0TkZlc)
  This tutorial has over 25 million views for a reason; it is probably the most in-depth and complete tutorial that I have ever seen. It starts with clear explanations before going on to explain three very different projects in detail. Again, if you have coded a fair amount before, this tutorial is likely not for you.

The second prerequisite is a basic understanding of [vector](<https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics)>) arithmetic. In particular, it is important to understand vector [addition/subtraction](https://en.wikipedia.org/wiki/Euclidean_vector#Addition_and_subtraction), [scalar multiplication](https://en.wikipedia.org/wiki/Euclidean_vector#Scalar_multiplication), [lengths (magnitudes)](https://en.wikipedia.org/wiki/Euclidean_vector#Length), and the [dot product](https://en.wikipedia.org/wiki/Euclidean_vector#Dot_product). The following resources offer a great introduction to vector arithmetic:

- [Wikipedia - Vectors (Basic Properties)](https://en.wikipedia.org/wiki/Euclidean_vector#Basic_properties)
  This section of the Wikipedia page provides a clear and consise explanation for all of the basic propties of a vector.
- [Unity - Understanding Vector Arithmetic](https://docs.unity3d.com/2019.3/Documentation/Manual/UnderstandingVectorArithmetic.html)
  This resource is somewhat [Unity](<https://en.wikipedia.org/wiki/Unity_(game_engine)>)-specific, but I feel like the demonstration of vectors as [objects](<https://en.wikipedia.org/wiki/Object_(computer_science)>) is valuable, and the explanations are clear.
- [MathsIsFun - Vectors](https://www.mathsisfun.com/algebra/vectors.html) and [MathsIsFun - Dot Product](https://www.mathsisfun.com/algebra/vectors-dot-product.html)
  Don't be fooled by the "unique" choice of fonts and "bold" usage of colours; MathsIsFun provides helpful diagrams and interactive demos that cover the material thoroughly.

## What are some useful learning resources?

![Image of an open book.](https://upload.wikimedia.org/wikipedia/commons/f/f9/Aufgeschlagenes_Buch_--_2020_--_4204.jpg)

<span style="opacity: 0.7"><a href="/wiki/User:XRay" title="User:XRay">Dietmar Rabich</a>&nbsp;/ <a href="/wiki/Main_Page" title="Main Page">Wikimedia Commons</a>&nbsp;/ <span class="plainlinks noprint"><a class="external text" href="https://commons.wikimedia.org/wiki/File:Aufgeschlagenes_Buch_--_2020_--_4204.jpg">“Aufgeschlagenes Buch -- 2020 -- 4204”</a></span>&nbsp;/ <span class="plainlinks noprint"><a rel="nofollow" class="external text" href="https://creativecommons.org/licenses/by-sa/4.0/">CC&nbsp;BY-SA&nbsp;4.0</a></span></span>

**The Ray Tracing Essentials YouTube Series by NVIDIA**
This series of YouTube videos provides a great starting point for learning about key concepts involved in ray tracing. In particular, I recommend watching the first two videos as they give you an overview of, firstly, how ray tracing works and, secondly, how [rasterisation](https://en.wikipedia.org/wiki/Rasterisation) works. This guide focuses on ray tracing, but it is nevertheless useful to understand the differences between the two approaches. If you are interested in the mathematical theory behind ray tracing, then Part 6 of the series explains it using a more mathematical approach, which is very fascinating.

- [Ray Tracing Essentials, Part 1: Basics of Ray Tracing](https://youtu.be/gBPNO6ruevk)
- [Ray Tracing Essentials, Part 2: Rasterization versus Ray Tracing](https://youtu.be/ynCxnR1i0QY)
- [Ray Tracing Essentials, Part 3: Ray Tracing Hardware](https://youtu.be/EoQfX1q-VNE)
- [Ray Tracing Essentials, Part 4: The Ray Tracing Pipeline](https://youtu.be/LoKUmbvbcRY)
- [Ray Tracing Essentials, Part 5: Ray Tracing Effects](https://youtu.be/Rk5nD8tt_W4)
- [Ray Tracing Essentials, Part 6: The Rendering Equation](https://youtu.be/AODo_RjJoUA)
- [Ray Tracing Essentials, Part 7: Denoising for Ray Tracing](https://youtu.be/6O2B9BZiZjQ)

**Ray-Sphere Intersection**

One of the first things that you will need to implement is some code to detect the intersection of a ray (a vector from a given point) and a [sphere](https://en.wikipedia.org/wiki/Sphere). [This webpage](https://www.scratchapixel.com/lessons/3d-basic-rendering/minimal-ray-tracer-rendering-simple-shapes/ray-sphere-intersection) provides a clear explanation of the problem along with further information about getting the [normal](<https://en.wikipedia.org/wiki/Normal_(geometry)>) and [texture coordinates](https://en.wikipedia.org/wiki/UV_mapping) at the intersection point. Additionally, [this YouTube video](https://youtu.be/OCZTVpfMSys) provides a fantastic visual explanation of ray-sphere intersection (note that it is within the context of rendering spherical atmospheres, not ray tracing specifically).

**Shooting Some Rays**
If you are proficient in vector arithmetic and confident in your coding skills, I suggest that you try to write your own code to shoot a ray for every [pixel](https://en.wikipedia.org/wiki/Pixel) that checks for collisions with a sphere. An example of how to do this can be found here:

- [Scratchapixel 2.0 - Implementing the Raytracing Algorithm](https://www.scratchapixel.com/lessons/3d-basic-rendering/introduction-to-ray-tracing/implementing-the-raytracing-algorithm)
  This webpage includes a minimalistic [pseudocode](https://en.wikipedia.org/wiki/Pseudocode) example that also computes illumination. I would have preferred it if they had built up the code over multiple steps, but it is nevertheless a good example.

**Code Examples**
I very much recommend trying to write your own implementations and to your project first, as this will strengthen your problem-solving abilities and give you a deeper insight into solutions. Additionally, it can be a lot of fun to come up with your own extensions to the project and to play around with different approaches. Afterwards, however, it is very valuable to look at how others approached these problems and structured their code. You could then consider changing your own code if you find worthwhile improvements. Here are some helpful [JavaScript](https://en.wikipedia.org/wiki/JavaScript) code examples that I have found:

- [RayTracer.js](https://github.com/ercang/raytracer-js)
  This simple ray tracer provides a fairly simple set of features, but it is very complete for what it is, and it is definitely worth a look at for its material system.

- [sundog.js](https://github.com/sporsh/sundog.js)
  If you are feeling brave, this **path** tracer has some really beautiful outputs when rendering glass objects of different shapes. A word of warning: path tracing is not quite the same as ray tracing, and I have no clue what "Monte Carlo integration" is!

If you are interested in the code that I produced with my friends, then you can find that project [here](https://github.com/Muirey03/MiniRay).

## How useful is ray tracing as a skill, and are simlar skills?

![Image of a sketched wighing scale.](https://upload.wikimedia.org/wikipedia/commons/c/c8/Sch%C3%BCtte_%26_P%C3%B6ppe_Fabrik_hauswirtschaftlicher_Maschinen_Hannover-Linden_Rechnung_1909-01-16_R%C3%BCckseite_Detail_IIIII.jpg)

<span style="opacity: 0.7"><a href="https://commons.wikimedia.org/wiki/File:Sch%C3%BCtte_%26_P%C3%B6ppe_Fabrik_hauswirtschaftlicher_Maschinen_Hannover-Linden_Rechnung_1909-01-16_R%C3%BCckseite_Detail_IIIII.jpg">differents</a>, <a href="https://creativecommons.org/licenses/by-sa/3.0">CC BY-SA 3.0</a>, via Wikimedia Commons</span>

Overall, since its [inception in 1968](<https://en.wikipedia.org/wiki/Ray_tracing_(graphics)#History>), there is no doubt that computer simulated ray tracing has been too slow compared to rasterisation for the majority of use cases. However, with the constantly growing advances in graphics card technologies, it is clear that ray tracing has made a comeback. We have now reached the stage where [full scenes can be rendered in real time](https://www.geeks3d.com/20210419/nvidia-rtx-tech-demo-the-attic-ray-tracing-unreal-engine/)! I think that it's safe to say that, due to this, ray tracing has a growing number of exciting and in-demand applications.

I hope that, like me, you will have been surprised by how easy ray tracing is to learn and the simplicity with which it operates. I would definitely say that learning about it has been well worth the effort, and it's certainly helped me learn some applications for all of the [linear algebra](https://en.wikipedia.org/wiki/Linear_algebra) I've had to study!

If you've enjoyed learning about ray tracing, why not investigate some other similar skills? [Ray marching](https://en.wikipedia.org/wiki/Volume_ray_casting#Ray_Marching) is a unique, but similar, approach, and [this](https://youtu.be/9U0XVdvQwAI) is an excellent demo showing off how powerful it is. Or you could look at [path tracing](https://en.wikipedia.org/wiki/Path_tracing) (like in sundog.js, which I mentioned earlier).
