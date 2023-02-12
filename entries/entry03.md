# Entry 3
## Tinkering With My Tool Pt.2 2/13/23

As the weeks passed, I have been tinkering more with my tool kaboom. I decided to tinker kaboom based on another tutorial because I felt that the YouTube tutorial didn't explain the scene-changing as well.I followed through a [tutorial](https://kaboomjs.com/doc/21-scenes) on kaboom that involved making many levels. I read through the tutorial step-by-step and coded along, while taking notes on the key components I might need for my freedom project.

The first component I took note of was the `onCollide()` function, which allowed for something to happen if something collided with one another. The tutorial used `onCollide()` for when the player collected coins:
```js
// when player collides with coin, the score increases by 1 and coin gets destroyed
player.onCollide("coin", (coin) => {
    destroy(coin) // destroy() removes sprite from scene
    play("score") // plays coin sounds
    score++ // increases score
    scoreLabel.text = score // updates the score #
})
```
`onCollide()` was also used for the portal, except it had different things inside it:
```js
// when player touches portal it'll check to see if there's another level, and if not, it will go to win scene
player.onCollide("portal", () => {
    play("portal") // play portal sound
    if (levelIdx < LEVELS.length - 1) { // will check to see if there are more levels after the level the player is currently in
        
        // will go to next level
        go("game", {
            levelIdx: levelIdx + 1,
            score: score,
        })
    } else {

        go("win", { score: score, }) // goes to win scene if there are no more levels after the level the player was in
    }
})
```
I took note of the onCollide() for the portal because it had a conditional that checked to see if there were more levels after the current level the player was in, and used that to determine which scene to go to next. 

I also learned how to make the screen go to a lose screen if the player fell off the platform: 


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
