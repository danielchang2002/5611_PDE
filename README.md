# CSCI 5611 Project 2: Physically-Based Animation with PDEs
Author: Daniel Chang (chan1975)

## Cloth simulation

Click [here](https://github.com/danielchang2002/5611_projects/tree/main/project2/cloth) for the code!

### Demo video

![img](https://raw.githubusercontent.com/danielchang2002/5611_PDE/main/cloth.png)
Click [here](https://www.youtube.com/watch?v=FkDdmKzh4CU&ab_channel=DanielChang) to watch the demo video!

### Features
- A 3D cloth simulation that supports one-way interaction with a spherical object (earth). (demonstrated in the whole video)
- A natural camera that allows the user to navigate around the scene using Minecraft creative mode style flying controls (demonstrated in the whole video)
  - shift/space => move down and up
  - WASD => move forward/backwards, left/right
  - mouse => move camera orientation
- High quality rendering, using an earth sphere texture, a Goldy the Gopher cloth texture, and directional 3D lighting
- User interaction: users can move the spherical object (earth) via mouse dragging (demonstrated at 0:12 seconds)
- Ripping/tearing: the spherical object can occasionally cause tears in the cloth! (Demonstrated at 0:34)

### Technologies used:
- Processing (Java)
- Used google images to find textures
- Used (and modified) code from canvas for camera
- Used Processing's example "nebula" texture

### Difficulties encountered
- It was difficult to ensure that the sphere did not render through the cloth when the cloth was close to the sphere. This was solved by increasing the radius of the cloth nodes.
- It was difficult to get the cloth's movement to be somewhat accurate. I achieved this by adding a pseudo "friction" force, that went against the direction of the velocity of each node at each timestep. I also increased the spring constant and damping factor. This required reducing the time step size dramatically.
- It was difficult to get accurate lighting and convincing 3D rendering. I did this by rendering two triangles for every group of four cloth nodes in a square shape. The normal for each vertex was computed by taking the cross product of the directions of the springs "above" and to the "left" of each cloth vertex. (for nodes on the left column and top row, the cross product was taken using the spring directions below and to the right)
- It was a bit tricky to implement the cloth tearing. I did this by tracking horizontal and vertical spring connections, severing them when they exceeded a certain proportion of the rest length, and did not render the cloth face if one of the springs of the face was severed.

## Fluid Simulation

Click [here](https://github.com/danielchang2002/5611_projects/tree/main/project2/fluid) for the code!

### Demo video

![img](https://raw.githubusercontent.com/danielchang2002/5611_PDE/main/cloth.png)
Click [here](https://www.youtube.com/watch?v=FkDdmKzh4CU&ab_channel=DanielChang) to watch the demo video!
