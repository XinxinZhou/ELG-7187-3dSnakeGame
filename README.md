# ELG-7187-3dSnakeGame

## Introduction

Our project is a 3D snake game, which is similar to traditional snake game but implemented in the 3D way. Users control the movement of the snake head to eat the food (rabbit). After successfully eating the food, the snake gets longer.

## Operation Mode
Users can control the snake through the keys “w, s, a, d”, and control the camera through pressing the key “1” (Number 1) and then the keys “u, o, i, k, j, l” (Details in the keyPressed() method in source code)

## Development Environment
Our project is implemented on Processing 2.1.1 and Maya. Both Processing 2.1.1 and Maya can be freely downloaded from the official website. Processing can be directly used after decompressing. Maya needs installation.


### Results of the Program
If I do not import the analyzing methods from assignment 1, which means there is no function of importing the models built outside the program. I am still able to implement the game. However, shown as Figure 1, it is not so vivid.

![](http://c1.staticflickr.com/9/8624/16716914172_69a4983764_z.jpg)
 
                 Figure 1. The version without importing the models

Thus, I imported the.obj analytic methods from assignment 1 and imported the models in .obj files. The result is shown as Figure 2.

 ![](http://c1.staticflickr.com/9/8608/16531862009_9cd7e108a2_c.jpg)

                 a)	Starting scene
 
![](http://c1.staticflickr.com/9/8646/16717984335_ec62bcf2f2_c.jpg)

                 b)	Running scene

 ![](http://c1.staticflickr.com/9/8621/16716913902_0bcd6de082_c.jpg)

                 c)	Change the viewing angle of the 3D scene

                 Figure 2. Different scenes of the game

## Contribution
In our project, I do all the coding work of the game and do some small work on the model, like do some adjustment to make the model suitable in the program.

## Implementation Detail of The Program
### Algorithm
The main process is that I build the snake head and food first. Then control the snake head through “w, s, a, d” on keyboard. If the snake head meets the food, add the snake body to the arrayList. Continuously updates the scene and check whether the snake eats the food or game over.

### Basic classes and methods
The programming language is Java on the Processing. And there are two .pde files in our program. One is named as snakeGame.pde, the other one is objViewer that is imported from the assignment 1-FFD, because we need to import the .obj fiels and draw the model in the program.
I used the basic architecture of processing - void setup() and void draw(), and also defined some class – SnakeBody, Food, GameStartBoard, GameOverBoard, briefly shown defined as follow:

* `class SnakeBody {`
* 	`int x, int y;     //the coordinate of the snake body.`
* `SnakeBody(int nX, int nY) {  // Constructor, initialize the position of the snake body.`
*    	 	`x = nX;`
*     	`y = nY;`
*   	`}`
* 	`void display (int option, char direction) {`
* 		`1. Translate (x, y, edge/2); // translate the model to the initial position.`
* `2. Use variable option to decide the head of the snake, or the body of the snake.`
* `3. Use variable direction to decide the rotation of the model. The original model faces only one direction. So when the moving direction change, the model should change following the direction.`
* `}`
* `}`
* 	`class Food {`
* 		`float x,y;`
* 		`Food() { //Constructor, give a random position to the food, limited in the map.`
* 			`x = int(random((uWidth/dim)-3))*(dim+2)+dim/2;   `
*   `y = int(random((uHeight/dim)-3))*(dim+2)+dim/2;   `
* `}`
* `void display() {`
* 	`translate(x,y, edge/2 - 10);  // move the model to the suitable position. `
* 	`drawObj(rabbit);  //draw the model.`
* `}`
* 	`}`
* 	`class GameStartBoard {} // Text, showing the instruction of the game.`
* 	`class GameOverBoard{} // Text, showing the message of the ending of the game.`

Also, there are some important methods defined in our program, setup(), draw(), keyPressed(), moveHead(), moveBody(), checkFood() and checkEnd(), briefly defined as followed.

* 	void setup() {
* 	Setup the basic 3D parameters.
* 	Define a snake head.
* 	Define a food.
* 	Load models from .obj files.}
* 	void draw() {
* 		lights();   // Set the default ambient light.
* 		Set the camera.
* 		Draw the map.
* 		Draw food.
* 		Draw snake.
* 		Move the snake head.
* 		Move the snake body.
* 		checkFood(), if the snake eats the food, add the snake body.
* 		checkEnd();
* }

* void keyPressed() {
* 	Hidden the text board.
* 	Control the direction of the snake head.
* 	Control the camera.
* }


* void moveHead() {
* 	Following the direction of the snake head, move the snake head.
* }

* void moveBody() {
* 	Traverse all the snake body parts.
* 	Make the latter follow the prior one.
* }

* boolean checkFood() {
* 	if(dist(coordinate of the snake head, coordinate of the food)<6){ 
* //dist() is library function which can return the distance between the snake head //and food here.
* return true;
* }
* 	return false;
* }

* void checkEnd() {
* if the snake head collides with the snake body, or the snake head collides the edge of the map, return the status of game over.
* }

### Lesson Learned
I have learnt a great deal about JAVA, openGL, Processing and Maya modeling in this project. I have learnt how to design the classes, methods, and using the architecture of Processing. I mainly consulted the references on the official website of Processing. Processing has a strong library of openGL, some integrated algorithm like distance calculation and an easier JAVA class structure (different from traditional JAVA structure), which makes it easier to implement a common 3D game.

Also, I have learnt how to model a character in Maya and do texture mapping by assigning the material to the model in Maya through the tutorial videos online. 

### Conclusion
We have basically finished the 3D snake game through coding in JAVA on Processing and modeling in Maya. In our game, users can control the snake to eat the food and change the position of the camera to provide a suitable viewing angle.
	
