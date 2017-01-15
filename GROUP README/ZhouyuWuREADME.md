Introduction

This document will explain the programming development of SCP093: The Red Sea Object. It will also discuss the personal contribution to Blueprints and some key game mechanics, which includes first-person character setup, level design, transportation between levels, heads-up display, and bug fixing. Many other minor adjustments will also be briefly explained below.


First Person Character

A ‘fake’ first person character was chosen to be our main character. It means that the character itself does not have a skeletal mesh or animation, so the character will not be shown in any reflective surface or seeing herself. In this case, most of the mirrors in the game are extremely blurred to reduce the error of noticing invisible character. The default first person template in Unreal was used and the VR content and shooting blueprints were cleaned up to fit our survival horror genre.

Due to the collision size and camera view of the character, the game environment should be built larger than the real world. Considering that most of the game will happen in the interior, our artists imported a modular set and other game assets which are about 1.5 times larger than real world references. However, there is a visual error in height and all the furniture looks higher in the camera. Therefore, I adjusted the camera height to fix this problem. In the game, the camera height is about 180 units (centimeters), but it looks like a normal eye height while playing the game.


Weapon System

Two actors, ‘Axe’ and ‘Gun’ were created and linked to the character. While they were picked up and added to the inventory, Boolean variables would be set ‘true’ and weapons would be activated. If weapons are picked up, the player can use key ‘1’ and ‘2’ to draw different weapons. However, players can drop items in the game, and a function to ‘force drop’ weapons was constructed in character blueprints. ‘Force drop’ means that if the player drops the axe/gun while holding them, it will be dropped and deactivated at the same time. I use the blueprint ‘Set Hidden in Game’ to toggle the activation of weapons; there is a similar ‘Toggle Visibility’ function in Unreal, but it redraws the mesh every time and takes extra memory in the game. 


Use weapons

Firing gun function uses the default template in the first person character. Respawn point, appearance, and the speed of bullets are adjusted to fit our new gun. Two original arms are cleaned because they did not fit the size of the new gun. The bullets are shot in front of the gun instead of the middle of the body. Waving the axe uses simple animation to rotate the axe actor when LMB is pressed. Leyla did the axe animation and I slightly adjusted the animation to improve the performance.


Transporting between levels

While transporting between levels, different PlayerStart points will be used so that the players will be spawned at different points on the map. For example, if the player transports from cellar to the house, he should be spawned in front of the cellar door instead of outside the house. To solve this problem, names for next PlayerStart points are cast in level trigger boxes, which are stored by Game Instance while transporting. In the beginning of a new level, a search function will be activated in the level blueprint to search for the correct PlayerStart point.


Storage Data across Levels

The inventory system was built up by Leyla and Abdullah, including variable ‘item data’ as the reference for searching items and displaying correct inventory lists. In addition, there are Boolean variables in both character Blueprint and Game Instance Blueprint. I suggested sing Game Instances as a storage of game data shared in all levels because all data in the inventory and the character will be lost in the new level. Variables related to every data are created in Game Instances; data is transported from the character to Game Instance while loading levels, and it is transported back to the character in the new level.


HUD setup

A new heads-up display is created to display user interface. It includes a health bar (Andrew and Leyla), bullet numbers (Leyla and me) and an instruction text (me). Bullets are limited in the game and the player has to search for supplies (water and bullets) during the game to restore health and bullets.

The instruction is provided by entering trigger boxes or checking certain requirements. If the player picks up certain items, different instructions will be given to suit the current progress. For example, if the diary is found in the bunker, the player should go back to the real world and complete the game. Therefore, ‘go back to the real world’ will be provided instead of the previous ‘search the house/cellar/bunker’ by checking Boolean variable ‘DiaryActive’ in Game Instances.


Bug Fixing

Minor bugs were fixed while testing the game. It includes minor changes of the actor such as enlarging the trigger boxes of opening doors and controlling the speed and angle of the mice. A flashlight was added to the character. After rendering, the interior looks much darker so that the player might need to turn on the flashlight in the room. It generates a better environment for a survival horror game. Other level blueprints such as flickering lights were added in the bunker as well.

Collectible items such as the letter, photo and diary are added in the game and they provide additional information about the parallel world. The player can open the inventory to check the details of these items, and a 2D image will be displayed for 2 seconds.

After the diary is activated, the player should go back to the real world and finish the game. Despite the change of instruction, enemies will not be spawned in other levels and items will not be refreshed again if you have already collected them. In the end of the game, the player can see the giant monster outside the level, which generates great horror atmosphere. The visibility of these monsters is also toggled by checking variable ‘DiaryActive’.


Conclusion

This project provides a great opportunity to collaborate with programmers. Most of the blueprints skills are learned from previous blueprints constructed by programmers, Unreal online documents, and video tutorials. The team members also help each other in different disciplines, and exchange knowledge about art, game design and programming. Blueprints such as AI, sound, Character, and Inventory contains programming works from different members as well.
