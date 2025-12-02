# Final Project

## Final Submission
#### Results
<img width="1920" height="1080" alt="render" src="https://github.com/user-attachments/assets/48fdd204-02e1-4169-894f-29daefc8e6a6" />

#### Implementations
I was able to effectively implement most of what I wanted to, especially seeing as I had to pivot my project only about a week ago I am proud of what I was able to accomplish. The main systems I was able to implement are:
- Procedural building generation with parameters for width, height, length, and seeding so that the windows and doors can be changed for each house
- Procedural asset placement on a plane with the ability to affect density of assets through Blender's weight painting mode
- Procedural animated snowfall using a noise texture plugged into the alpha channel of a principled BSDF material
- Procedural icy snow material using voronoi noise and bump and displacement mapping
All of these implementations were done using Blender's node-based systems of Geometry Nodes and Shader Nodes. I enjoyed learning a new procedural workflow while also being able to see the similarities and transfer my knowledge from other technologies used in class. The labs and homeworks done in Unity Shader Graph and Houdini were especially helpful since they were also node-based.

#### Challenges
- Triangle Roof: The roof shape, although simple, proved to be one of the most difficult parts to implement. The video tutorial that I followed created a square building and just added a simple grid for the roof. Becuase I wanted the houses to look like cottages, I needed to instead use a cone geometry node with 4 vertices. The issue here was that the cone vertices were a 45 degree rotation different from the corners of the building. I spent a while trying to figure out some combination of numbers to multiply and add to the scaling of the roof, but this gave me no success. Eventually I was able to solve the issue by adding a rotation to the cone and passing that to a new geometry node before scaling, it was really an order of operations issue which can be hard to figure out when working with nodes.
- Randomness of Buildings: The main issue I came across was when passing the procedural building to the plane it was scattered on because it simply placed the same house at each instance instead of allowing me to randomize dimensions and windows and doors across instances. I figured out how to pass the geometry nodes output from the building to the instance variable of the plane, but still even with the ability to directly select inputs for these parameters it applied them to all instances. I had to use my last choice option for the variance of the buildings, which was to have a few instances of the building and change the dimensions as well as window and door placement for each and then using a collection of these buildings as the input to the instances, which randomized their placement. I hope to find some way to set ranges of values for these parameters in the future so that they can be parameterized.

#### Future Improvements
- More Proceduralization: As I said above, I would want to improve/add the parameterization and randomness of building dimensions and window and door placement.
- Building Improvements: Because modeling was not my focus, the assets are very simple. I would want to add more interest to the current assets as well as create more types of assets and buildings such as creating a procedural generator for churches or having more colors for the houses or more doors, etc.
- More Assets: I also understand that because the scene is only buildings it creates quite a simple scene, so I would like to create more assets for the scene. I thought about adding some sort of walkway or road that looks like cobblestone, stylized pine trees, and lamp posts. I would probably implement all of these procedurally, maybe through a shader on the cobblestone road and through geometry nodes with the trees and lamps.

## Design Doc
#### Introduction
What motivates your project?
- I've been wanting to learn more about Blender and proceduralism in Blender all year but haven't had a chance to. I've seen some tutorials from artists I follow about creating stylized buildings of this style and I want to utilize them in this project because I enjoy the stylized look and think putting a scene together would teach me about composition.

#### Goal
What do you intend to achieve with this project?
- I want to learn while also creating a project that showcases procedural placement and generation in order to create a stylized scene.

#### Inspiration/reference:
<img width="600" alt="image" src="https://github.com/user-attachments/assets/a6fa8e85-1124-4c1c-a5e7-d5582a70228c" />
<br />
Above: https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.fab.com%2Flistings%2F59e33f20-d49d-4269-8e07-e2a8cf396426&psig=AOvVaw0vrpQ5UKEsMZ50E5rEYAnT&ust=1764125897224000&source=images&cd=vfe&opi=89978449&ved=0CBYQjRxqFwoTCKCg2p2njJEDFQAAAAAdAAAAABAL
<br />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/01f4f131-9b12-44c8-8a99-0deaa7189f9a" />
<br />
Above: https://justcreate3d.itch.io/stylized-medieval-village
<br />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/c8d37a1f-f1da-43a5-adc2-b8026a104588" />
<br />
Above: https://www.etsy.com/listing/4338398063/christmas-town-snowy-village-winter

#### Specification:
Outline the main features of your project:
- Modeled village buildings, probably one hero building
- Procedural setup for randomized placement of buildings
- Props such as snow, lights, bridge possible
- Basic materials applied

#### Techniques:
What are the main technical/algorithmic tools you’ll be using? Give an overview, citing specific papers/articles.
- I will be using the open-source 3D software Blender for all aspects, I will not need plug ins as far as I know. I plan to use some modeling tutorials from Grant Abbitt and some procedural village/city videos, possibly one of these: https://www.youtube.com/watch?v=MRYJeBUhSx4 or https://www.youtube.com/watch?v=pYHocEhwPr0

#### Design:
- How will your program fit together? Make a simple free-body diagram illustrating the pieces.

#### Timeline:
Note: Timeline is adjusted from normal project guidelines because I switched projects
| Timeline | Goal |
| ----------- | ----------- |
| Nov 22 - Nov 24 | Gather reference materials, including inspiration images and relevant Blender tutorials |
| Nov 24 - Nov 26 | Procedural layout is set up, models of varying houses are made |
| Nov 26 - Dec 1 | A complete procedural village scene that has been rendered with basic materials |

## Milestone 1
I found multiple helpful tutorials on YouTube for what I want to implement, and I originally used CGEssential's YouTube tutorial on how to place objects randomly using a particle system, but this was an old tutorial and I ended up finding a better tutorial from the same creator on how to procedurally place buildings and alter parameters like the density, scale, rotation, etc. using Blender's weight paint mode. This setup is done using Blender's geometry nodes with the main two nodes being Distribute Points on Faces and Instance on Points which places an item at each instance. I had some issues with the weight painting at first but then realized that the issue was due to the plane not being subdivided and only having four vertices. I created a very basic instance of a house to place to show a proof of concept.

<img width="800" height="693" alt="image" src="https://github.com/user-attachments/assets/14d28a45-29b3-4442-a619-a19bf10877a2" />
<br />
Above: Geometry Node Setup
<br />
<img width="800" height="829" alt="image" src="https://github.com/user-attachments/assets/904cbe9e-29d7-45a6-9d8f-f55e98e7724f" />
<br />
Above: Weight Painted Plane with Buildings
<br />
<img width="333" height="501" alt="image" src="https://github.com/user-attachments/assets/38e9cc37-86e6-4f08-9419-f522967cec95" />
<br />
Above: Parameters used to create the current model/scene


## Milestone 2
Currently working on creating procedural buildings using this tutorial: https://www.youtube.com/watch?v=-rexNuTap44&list=PLcRX9rXhXHWiaRgVPCdp8811YLsGdDeK7
<br />
I am just updating this at 11:27pm on November 24th, so I don't have time to create the entire asset pack that I am going to use when generating my own procedural building, but here is an image of a wall that I created with the type of style I want to emulate for the buildings in my piece:
<br />
<img width="800" height="695" alt="image" src="https://github.com/user-attachments/assets/34791056-1ffb-4081-8c14-29a595d834e3" />
<br />
Using the tutorial assets, this is the building output I was able to generate:
<br />
<img width="800" height="656" alt="image" src="https://github.com/user-attachments/assets/e6a50a17-2f66-41c0-b697-c17002227158" />
<img width="800" alt="image" src="proceduralBuilding.gif" />
<br />
My next step is to create the rest of the modular asset pack in the cozy village style that I want, and then swap the pink and white assets out for the cozy village ones in order to create the procedural models that will be placed on the plane in the final scene.

Submission:
- Push all your code / files to your repository
- Come to class ready to present your finished project
- Update your README with two sections
  - final results with images and a live demo if possible
  - post mortem: how did your project go overall? Did you accomplish your goals? Did you have to pivot?
