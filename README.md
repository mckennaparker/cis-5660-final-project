# Final Project
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


## Milestone 2: Implementation part 2 (due 11/24)
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


## Final submission (due 12/1)
Time to polish! Spen this last week of your project using your generator to produce beautiful output. Add textures, tune parameters, play with colors, play with camera animation. Take the feedback from class critques and use it to take your project to the next level.

Submission:
- Push all your code / files to your repository
- Come to class ready to present your finished project
- Update your README with two sections 
  - final results with images and a live demo if possible
  - post mortem: how did your project go overall? Did you accomplish your goals? Did you have to pivot?
