# Wheeled-Arm-
[e-ATV]-
Satyendranath Bose Summer Internship, 2021






---------------
#Wheeled Bot
---------------
URDF File

Pose and inertial
Here we have link because we have a link of the robot. So we have inside the link some basic properties that are mandatories. So we have to define the pose of this link for instance we are defining here we have XY and Z and then roll pitch and we are defining everything zero except Z because we don't want the chassis to touch the ground. After that we have to define the inertial properties so we start telling the mass of the object so we are putting here just 5 kilograms just sure to have something a good value to work with and then the origin of the mass so we are using the same that we are using for the pose of the link and then the inertia matrix so we need six values here. 

Collision
  After the inertia we have to define the collision property which is basically telling the simulator the dimensions of this object the dimensions that must be used to calculate the collision when this object a farthest object can collide with other objects in the scene so inside the collision we have only this geometry property and for the chassis we are defined this is a box and the dimensions X Y Z after that we close the properties geometry and collision.

Visual
    After that here is the visual property which is basically almost the same as the collision but actually it's not used by the simulator to calculate the collisions between objects but used to generate the visualization we are going to have of the object in the simulator so this is just the visual of the object. It's not important for the dynamics of the simulation. We're using the same value as the collision so we are looking at the same object we have colliding in the scene. And we are also defining here this property material with this name blue which is basically just the color to put in the material. 

Caster Wheel Front
   So after having the main body of the chassis we have to define also the caster wheel so as we can see here the robots have this caster wheel to points touching the ground so the robot won't be falling and kicking on the ground all the time and we are defining it not as another link we could do this as another link here in front of the robot but to make it easier we are just defining here together with the chassis. And here we are defining the collision of the caster wheel and here the origin row pitch and X Y and Z. And the geometry this is a sphere and that's the radius of the sphere. And this surface property is basically used to define the forces between the surfaces that the caster  wheel is touching the ground so we have to define the forces between them in this case this is 0 and this is the property just to tell that they are going to have no forces between this two surfaces. And after that this is the visual of the caster wheel which is basically the same way we have done before. 
 
Right Wheel
     And here is the next link and it is the right wheel. And we have the inertial again and the collision and visual this is just the most basic properties. And here we are defining the geometry cylinder because this is a wheel so in order to have the right wheel attach it to the chassis we have to create a joint. And here is the joint name "joint right wheel" and type is "continuous". And after that we have also to define the origin and that's exactly the position we are going to place the wheel in the chassis. And here is the child link and parent link property. *Child link name must be same as the link name and parent link name must be same as the chassis name* . And this is the axis where this joint is going to rotate around. In this case it rotating over the Y-axis. And it is just some values to make everything work here. 

 Left Wheel 
We are doing basically the same thing for the left and the right wheel just only difference is the position of the joint. 
...............................................................................................................................................................................







RVIZ.Launch
We are defining here the robot description parameter(ROS Parameter). And we are using the cat command to read the file. 
  And here we are publishing the joint state of the joints of the robot and the robot state and the robot state publisher. 
   And the final thing is starting RVIZ using the argument passing the package as an argument 

Spawn.Launch
We have this launch file here and the parameter we are using Robot Description. And here we are defining three arguments X, Y and Z which is basically the composition of the initial position of the robot and the environment. 
 And here we are creating this node that's going to execute the test to spawn the robot and sign the environment and it comes from the package called gazebo_ros and this spawn_model and here is the output screen and here the argument and we are passing the argument URDF because this is a robot described using URDF language format and it's parameter we are using robot description which represents the description of the robot we have just created and here the name of the model  and this argument is same as the above arguments. We are defining it in the above because if we want we can change these values in the command line when we call the ROS Launch File. So we are just passing the arguments here.

...............................................................................................................................................................................





