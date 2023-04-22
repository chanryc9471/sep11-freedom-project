# Entry 5
## Finishing MVP 4/24/23

In my previous blog, I started on my freedom project Minimum Viable Product (MVP) while also learning my tool for something beyond MVP. In this blog entry, I'm finishing up my MVP and also learning about looping the levels. 

After loading in the sprites, me and my partner started making the maps:

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
In order for the maps to work and for the sprites to be on the webpage, my partner and I assigned symbols to the sprites like so:
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
The `solid()` gives the sprite an area, not allowing another object to move pass it. In addition, the `body()` gives the sprite a physical body to be able to respond to gravity. Furthermore, my partner and I made it so that the sprite was able to move. 

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
