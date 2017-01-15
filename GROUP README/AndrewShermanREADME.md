Creating this project has been a fairly large challenge from the start. While I had some good experience doing programming in Unity using C# this was my first time sitting down and actually using the Blueprints system for Unreal 4. What this meant was trying to figure out a node based system for programming instead of just written. After awhile, it became easier to understand what I was doing even though it still could be frustrating at time to work with.


The portions of the project I was responsible for in respect to coding were the health bar UI as well as the AI for our enemy “shades”. When it came to creating the health bar it was actually quite simple. UI changes are made through the Unreal HUD widget that are in every project. From there you add simple elements that can be modified from their respective detail panels. What follows is that each piece of the HUD has to be setup correctly to fit into whatever size specifications that you need, as well as anchor points and linking the healthbar progress bar component to an external variable. A health variable had to be setup in the first person character BP and setup to subtract from that variable when the first person character came into contact with enemies.


![Healthbar](http://i.imgur.com/kAjmg8y.png)


Next was creating the AI. The original AI was first setup by Sabrina, however I wanted it to do more complex actions and I wanted it tied to something else other than the basic model we originally had it attached to. I imported the Unreal third person character model and began to implement the original AI, however with some changes when it came to detecting the player character. From there I had to create a system where the AI wasn’t just going to stand there and wait until the player came into range in order to react. In order to do this I used the AI Move To function with an input from another function that created random coordinated based on the NavMesh that was present in the level. From there there had to be a series of boolean variables that regulated when the AI was simply roaming or it was attempting to follow and attack the player. This was achieved using various branches that were tied to booleans that were set whenever the player entered or left the radius of the AI. What this led to was a simple AI that would target a random set of coordinated then move to them over and over again until the player was within range. 


![AI](http://i.imgur.com/rOax5zO.png)


The blueprint system also extended into creating materials, especially for laying the groundwork for material instances. If anything, when creating a material in Unreal 4, you are more like programming a shader to do what you want. Many of the blueprint functions are inside the material editor and can be used to create interesting things. In our project I used this to create several material instances with different features, such as Albedo only, to Albedo and Normals, or Albedo, Normals, Roughness, Metalness. 
![Materials](http://anda02.imgur.com/all/#1)
This video shows how the AI behaves in a simple game environment.


https://www.youtube.com/watch?v=C_2BPcaAEIc&feature=youtu.be