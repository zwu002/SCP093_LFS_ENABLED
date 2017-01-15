#Leyla Mammadova  (MSc Computer Games and Entertainment)
I was taking part as one of the programmers in this project. I will try to briefly describe my work starting from the beginning. 
Since this game is mostly about learning the environment and finding clues, one of the first things that was need to be build is inventory.
I got help in creating that from standard Unreal tutorial, with additions of UI and some features that wasn’t used in tutorial. 
In their tutorial, they could only pick up and spawn one type of object, fixing picking up different object was easy by creating different actor class, but dropping different objects was I bit of challenge.
Whenever you dropped an item, it respawned an actor array with the same index. 
For example, in your inventory array gun is number 3, but in actor array it is number 2 and axe is number 3, 
so when you want to drop gun it will drop an axe. 
To fix that I used an inventory structure to hold information of which class is used and needs to be respawned. Problem got fixed. 
I’ve build a simple inventory UI that is called when you press I. 
The speed of out character movement was slow, so to sprint you need to hold the Shift button like basically in every game. 
When you hold shift, it calls a function that increase the maximum walking speed of the character. 
You can adjust the preferable speed easily through FPC blueprint.
I’ve created the first AI, at first it was just a sphere that start to chaise the character when AI see it. 
Also, I connected the AI to apply damage on our character. The health start to decrease a soon as AI it touching our character. 
Made the gun destroy our AI with 3 successful shots. 
To make this small project more big game look alike I’ve created the game over and loading game widget (the design was made by artist),
when you get “killed” by our AI it creates a widget that allows you to respawn at the beginning of the current level. Also, when you travel
through the levels you see a level loading widget.
Since our axe wasn’t a skeletal mesh, I’ve added a timeline so when you hit left mouse button it activates the axe. 
Made gun follow the camera for aiming. 
Our character is also able to pick up and through physics objects depending of which force he applies to them.
Also, when you step on bullets they add ammo, and when you step on water bottles they add health.
Misc: physics, collision and other bugs fixed, destructible meshes creations, whoosh bang sound, displaying the diary, letter, and photo. 
