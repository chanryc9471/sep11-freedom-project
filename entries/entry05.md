# Entry 5
## Finishing MVP 4/24/23

In my previous blog, I started on my freedom project Minimum Viable Product (MVP) while also learning my tool for something beyond MVP. In this blog entry, I'm finishing up my MVP and also learning about looping the levels. 

After loading in the sprites, my partner and I started making the maps:

```js
const maps = [
	[

		'                                     ',
		'                                     ',
		'                                     ',
		'                                     ',
		'                                     ',
		'                                     ',
		'                                     ',
		'          ###                        ',
		'         ====                        ',
		'                ####          &      ',
		'========       ======   ========     ',

	],
	[

		'                                     ',
		'                                     ',
		'                                     ',
		'                                     ',
		'                                     ',
		'                       @ ##     &    ',
		'                !!!!!!!!!!!!   !!!   ',
		'       ##  !!!                       ',
		'      !!!!                           ',
		'  ##      @                          ',
		'!!!!!!!!!!!!!!!!!!      !!!!!!!!     ',

	],
	[
		'                                     ',
		'                                     ',
		'                                     ',
		'                      %%%%           ',
		'                         %           ',
		'                      ###%           ',
		'                     %%%%%           ',
		'           #     @              ',
		'      #   %%%   %%%            &     ',
		'     %%%      @           %%%%%%     ',
		'%%%         %%%%%    %%%             ',

	],

]
```
For the maps to work and for the sprites to be on the webpage, my partner and I assigned symbols to the sprites like so:
```js
const levelCfg = {
		width:45,
		height:50,
		'=': [sprite('o-block'),solid()],
		'#': [sprite('coin'), 'coin'],
		'&': [sprite('door'), 'door'],
		'!': [sprite('y-block'),solid()],
		'@': [sprite('enemy'),'enemy',solid(), body()],
		'%': [sprite('g-block'),solid()]

	}
```
The `solid()` gave the sprite an area, not allowing another object to move pass it. In addition, the `body()` gave the sprite a physical body to be able to respond to gravity. 

After the sprites and the map, my partner and I made it so that the main sprite was able to move on the blocks. We used `keyDown()` to 	allow the player to move left and right with the arrow keys and `keyPress()` to jump with the spacebar key:
```js

// left arrow key
keyDown('left',()=>{
		player.move(-MOVE_SPEED,0)
	})

// right arrow key
	keyDown('right',()=>{
		player.move(MOVE_SPEED,0)
	})
// spacebar key
	keyPress('space',()=>{
		if(player.grounded()){
			player.jump(JUMP_FORCE) // JUMP_FORCE is how much force is in the jump
		}
	})
```
After my partner and I got the sprite to move, we used `.collides()` to have the sprite able to collect coins and go to the next level with a door sprite. If the sprite collided with a coin, then the user score would increase by one. Every time the user sprite collided with the door, the user would go onto the next level. If the user collided with an enemy, then the user would be prompted to the lose scene where it shows their score. Additionally, I prompted the webpage to go to the lose scene if the user were to fall off the platform:
```js
	player.action(() => {
		camPos(player.pos)
		if(player.pos.y >= DEATH){
			go('lose', {score: scoreLabel.value})
		}
	})
```
If the player's y-position reaches greater than the value of `DEATH`, then the webpage would go to the lose scene. Inside the `player.action()` was also code that made the camera follow the player with `camPos(player.pos)` by setting the camera position to the player position. 

As the last step, we made a score counter that would increase as the player collected or collided with the coins. There was also a level counter that the player would see at the start of each level.

After I finished my MVP, I went on to learn how to loop the levels that way there would never be an end to the game. I learned from a [YouTube video that used kaboomjs to make a Mario game](https://youtu.be/2nucjefSr6I) how to loop the levels. In the place where the player collided with the door and would be led to the next level, I added `% maps.length` to `level:(level + 1)` so when the player reaches level 2, it would increase by one and divided by the maps.length, making the webpage go back to the first level.

I'm currently in stages 5 and 6 of the Engineering Design Process (EDP), which is creating a prototype while testing and evaluating the prototype. I finished my MVP, and I was testing my code while I was adding on the components that would allow the game to function as it should. 

Skills that I have come to develop in this blog entry are *organization* and *communication*. Especially when my partner and I were coding a bunch for our MVP, we had to organize the code into categories using comments. It ultimately helped us a lot when we worked on different parts of the project, and the comments helped a lot with figuring out what code did what and which code was to go first, next, or last. There was communication happening throughout our MVP coding as we were updating each other frequently whenever we added/pushed to the project so that we would know when to pull new code into our codespaces. As a result, it helped us prevent any major merge conflicts.

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
