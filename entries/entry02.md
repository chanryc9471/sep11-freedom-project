# Entry 2
## Tinkering With My Tool 12/19/22

For the past few weeks, I have been tinkering and trying to learn the components of [kaboom](https://kaboomjs.com/) I would use on my freedom project. First off, I explored the [kaboom playground](https://kaboomjs.com/play?demo=add) and dove deeper into the code to learn the concepts. I looked at things like loading in a sprite, using arrow keys to move, gravity force, jump force, making a map with symbols, and colliding sprites with each other. I tinkered with the speed of the player's movement, which had to do with the arrow keys that moved the player.
```js
// left arrow key
onKeyDown("left", () => {
		player.move(-SPEED, 0)
	})
  
// right arrow key
onKeyDown("right", () => {
		player.move(SPEED, 0)
	})
  
// up arrow key
onKeyDown("up", () => {
	player.move(0, -SPEED)
})

// down arrow key
onKeyDown("down", () => {
	player.move(0, SPEED)
```
I learned that `-SPEED` was to move the player to the left and that `SPEED` was to move the player to the right. When it came to the up and down arrow keys, the speed was flipped. `-SPEED` would be going up, and `SPEED` would be going down. Gravity force and jump force were interesting as they were the opposite of each other. The lower the gravity force value, the longer it took for the sprite to fall to the ground after it jumped. For the jump force, the higher the value, the higher the player would jump.

The most important components that I learned was the scenes and maps. I would need it in order to create different levels in my platformer game. There are different symbols that represent the different sprites that load on the map. The map was super customizable, which I liked.
```js
const LEVELS = [
	[
		"@  ^ $$ >",
		"=========",
	],
	[
		"@   $   >",
		"=   =   =",
	],
]
```

Now that I had a basic understanding of the components of kaboom, I followed a [youtube video](https://youtu.be/37rASpfnCCM) to create a small platformer game to test my knowledge. I followed through with most of the video and created a [small project](https://kaboom-tinker.chanryc9471.repl.co/). I learned how to make a lose and win screen like so:
```js
// lose scene
scene('lose', () => {
  add([
    text('You Lose!'),
    color(255, 0, 0),
    origin('center'),
    pos(width() / 2, height() / 2)
  ])

  onKeyPress(() => {
    go('game')
  })
})

// win scene
scene('win', () => {
  add([
    text('You Win!'),
    color(0, 255, 0),
    origin('center'),
    pos(width() / 2, height() / 2)
  ])

  onKeyPress(() => {
    go('game')
  })
})
```

I'm currently in stage 2 of the Engineering Design Process, which is **researching the problem**. I researched the components of my tool, and tinkered with it to better understand what I could do with kaboom. I also followed along with a youtube video to familiarize myself with kaboom.

Skills that I have developed in this blog are *how to learn* and *how to read*. When I was looking through the kaboom playground demos, I saw many parts of kaboom, but there were no explanations on what each code did. I had to reference the documentation in order to further understand what the code was meant to do. In doing this, I learned and tinkered with the components that would be useful when I start to make a platformer game.

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
