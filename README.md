# webGL

This is Moesaeah here, and for my exploration I decided to dive into Interactive 3D and 2D graphics within the web browser. More specifically I used Mozilla’s WebGL (Web Graphics Library). WebGL is a Javascript (JS) API for rendering 2D and 3D graphics in compatible browsers without the need to use Plugins. It does so, by “Introducing an API that closely conforms to OpenGL ES 2.0 that can be used in HTML5 <canvas> elements.

Check out official information here:
https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API

In order to make an easy to follow guide, and a way for people with no experience in 3D programming I used ThreeJS. 

Found here: 
		https://threejs.org/

ThreeJS is a library to make WebGL easier. Since WebGL is an API that allows the developer to access a computers specialized graphics hardware using JS.  

My goal for this exploration was to create an animated rotating 3-Dimensional shape that would translate from side to side. I explored not only 3D graphics, shapes, Materials, Rotations and Translations. 



The biggest problems I faced was the getting the shape to move side to side at very smooth speed and then leave the trail of its past position behind.  

Check out what I was able to make: 
ec2-34-204-48-114.compute-1.amazonaws.com/3DSample.html

For an in-depth guide to three.js/webGL go to: 
https://threejs.org/docs/index.html#manual/introduction/Creating-a-scene

JOURNAL
1.	You will need to set up your HTML file like so:
a.	<!DOCTYPE html> <html> <head> <meta charset=utf-8> <title>My first three.js app</title> <style> body { margin: 0; } canvas { width: 100%; height: 100% } </style> </head> <body> <script src="js/three.js"></script> <script> // Our Javascript will go here. </script> </body> </html>

2.	You will need access to ThreeJS library, you can obtain it here:
a.	three.js
3.	Now, you need to check if the person browser can render our 3D space by adding this: 
a.	<script src="http://brangerbriz.net/labs/threejs_playGnd/js/Detector.js"></script>
4.	Now, just add another set of script tags. 
a.	if (!Detector.webgl) Detector.addGetWebGLMessage();
b.	this is to make a check about the browser and the person’s hardware computer before attempting to render the program. 
5.	Now we need to make our composition, so we need to define our camera, scene, renderer. These three things are essential for creating the 3D dimensional space, and preparing it for the user to be able to see the shapes we add into it. 
6.	Time to make the shapes, and it’s necessary attributes like the material and mesh.
7.	I created a function called setup()
a.	All of which will create the composition for our scene. 
b.	The height and width of our scene, and preserve
8.	Now we set render of our scene from the default color of clear the color black and then load it when the DOM is loaded. 
9.	From this point, we create the scene and add shape to it. When defining our material, we can define how our shape will look. 
10.	Now we add the meshes too the shape. Of which we can control the scale, rotation, and additionally shadows. Essentially Meshes will control the vertices of the shape. The shape I chose is Icosahedron. 
11.	Add Wgeometry/wmaterial and change the plane making our shape appear to more wireframed.
12.	Now time to move our shape across our scene from side to side. I created the function Draw to do just this.  By calling a requestAnimationFrame(draw);
a.	From this point we move the mesh positions of x and we can also give it that trailing affect like in my example the mesh on the z access, but changing the time it stays within the z-access
13.	Now we call the two functions we make our shape move. 
