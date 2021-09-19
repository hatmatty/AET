

## ![alt text](GithubLogo.png)
> *Ancient Era Tech*

## Purpose

For far too long the ancient genre has not been able to come to widespread adoption of a new technology. We believe this is because new ancient genre technologies contain some of the following:

1. a lack of customizability
2. a hard to learn combat system 
3. or a lack of combat depth 
3. not being open sourced

AET plans to change this by introducing a combat system which has almost no initial learning curve yet retains depth and is open sourced and easily customizable. Below you'll find some of planned features which we hope will set apart this system from others and lead it to widespread adoption.

## Game Components

### Config
> Files: [Config]
- This is where you can edit gametype (such as R15/R6), and enable or disable various toggleable game componnets. 

### Camera
> Files: [CameraController]
- Manages various cameras such as the first person and spring camera and ensures that they do not have to directly interact with each other. 
	#### First Person Camera | low priority 
	> Toggleable, Files: [FirstPerson]
	- Manages the creation and destruction of a first person camera on the player.
	#### Spring Camera
	> Toggleable, Files: [Spring]
	- Manages the creation and destruction of a spring camera on the player. Utilizes spring module. 

### BodyRotator
> Toggleable, Files: [BodyRotaterService, BodyRotaterController]
- Tracks camera rotation and rotates the body accordingly. This is what allows for the directional combat however it can be completely disabled.

### Sprinting 
> Toggleable, Files: [SprintingService, SprintingController]
- Player should be able to toggle sprinting across the map. Sprinting will not have to interact with many modules of the game allowing it to easily be disabled and enabled by game devs. 

### Tools
> Files: [ToolService]
- There tool service handles the giving of tools (weapons, shields, etc) to players. This system is diverse and flexible, allowing for the creation of spears, bow & arrows, etc. 
	#### Tool
	> Files: [Tool]
	- This is a component which attaches to the a tool model and directly utilizes actionpacks.
	#### ActionPack
	> Files: [Essential, Weapon, Shield]
	- An actionpack creates several actions and packs them into one unit. This is important because these actions frequently communicate with each other through creating new attributes in the Action and Tool classes. If an action sets an attribute in the Action class it means it only expects other methods in the action (start, cancel, finish) to utilize it. If it sets an attribute in the Tool class it means it expects other actions in the action pack to utilize it (such as the holster action and equip action disabling the other animation which was set to an attribute of the tool when they start).
	#### Action
	> Files: [Action]
	- An action consists of the following methods: start, cancel, and finish. It has one main variable which is accessed by the tool called "state". 



