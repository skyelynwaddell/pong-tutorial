## Goal
Making pong in gm studio with as as little lines of code as possible, within 10 minutes.

## Audience
To show how a simple application may work for someone who has never programmed or made a game before.
Anyone can follow this task who wants to make a simple game in pong and you can download the gm studio ide from the website .
You will need gmstudio, a computer as well as a little bit of thinking.

## Cautionaries
1. lets setup the project with the Correct name

2. lets make sure our window size is correct

3. lets make sure we have all the objects and sprite necessary for this to work

## Steps
1. Make a new project in gm studio
2. Change game name, and window size
3. Add objects
	-oBall
	-oPaddle
	-oPlayer
	-oEnemy
4. Add Sprites
	-sBall
	-sPaddle
5. Make the oPlayer & oEnemy children of the oPaddle

## Program oBall

### Create Event
```js
//set the ball's initial speed
randomize()
spd = 5
hspeed = choose(spd,-spd);
```

### Step Event
```js
//check if ball is touching the roof or floor
if (bbox_bottom > room_height) or (bbox_top < 0) 
	vspeed = -vspeed

//check if the ball went in a net
if (x < 0 or x > room_width) {
	game_restart()
}
```

### Collision with oPaddle
```js
//check which side of the room the ball is on
if (x < room_width * 0.5 and hspeed <= 0)
or (x > room_width * 0.5 and hspeed >= 0)
	hspeed = -hspeed * 1.05 //flip the ball's direction

//give the ball some random vertical speed
vspeed = random_range(-5,5)
```

## Program oPlayer

### Step Event
```js
//make the player follow the mouse
y = lerp(y,mouse_y,0.1)
```
## Program oEnemy

### Step Event
```js
//make the enemy follow the ball
y = lerp(y,oBall.y,0.08)
```

## Conclusion
Now you should see how a simple application like Pong could work in a game, as well as how simple logic is calculated and decided when in game, and that programming isn't hard and that you can learn things if you take time to!
