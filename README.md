Savannah Dash

My game is inspired by Crossy Road, where players have to navigate through a Savannah environment and avoid moving animals. The aim of the game is to travel as far as you can and earn points without losing all three lives. Players use the arrow keys to move their player.
> Link to game here: https://makecode.com/_503EYFJyLTYa


## Table of Contents
* (#general-information)
* (#technologies-used)
* (#features)
* (#screenshots)
* (#setup)
* (#usage)
* (#project-status)
* (#room-for-improvement)
* (#acknowledgements)
* (#contact)



## General Information
I created a game called Savannah Dash using Python in MakeCode Arcade. Players control a bunny character moving through a savannah environment while avoiding lions. The purpose of my project was to create a fun and interactive game while developing my coding skills. Although my project doesn't solve a specific problem, it focuses on creating an engaging gaming experience. I chose to create Savannah Dash because I like Crossy Road and wanted to develop my own version with a different theme.


## Technologies Used
 Python in MakeCode Arcade


## Features
 Player Movement: Players use the arrow keys to move their character and avoid lions.
Randomly Generated Animals: Animals appear at random positions and move in different directions, making the game unpredictable and fun.
Scrolling Background: The camera follows the player as they move forward, allowing the game to continue beyond one screen.
Scoring System: Players earn points each time they reach a new high position.
Three-Life System: Players start with three lives and lose one when they collide with an animal The game ends when all lives are lost.
Increasing Difficulty: Animals move faster as the game progresses, making them harder to avoid.
Collision Detection: The game detects when the player touches an animal and triggers a visual effect and noise when a collision occurs.


## Screenshots
<img width="801" height="207" alt="Screenshot 2026-11-03 at 2 33 07 pm" src="https://github.com/user-attachments/assets/ca1cc567-f133-463f-95e6-5b7d4235c3c6" />
<img width="986" height="749" alt="Screenshot 2026-11-03 at 2 25 15 pm" src="https://github.com/user-attachments/assets/1947e1ea-1ed9-4183-9e43-ecbd617c4ed4" />
<img width="1654" height="803" alt="Screenshot 2026-11-03 at 2 07 22 pm" src="https://github.com/user-attachments/assets/a0025330-8248-4232-9c16-d1016390ccd8" />



## Setup
Python in MakeCode Arcade
My project did not require any additional software installations or external Python libraries. 
Open MakeCode Arcade.
Click New Project to create a game.
Switch the editor to Python.


## Usage
Savannah Dash can be played through the MakeCode Arcade simulator.
Arrow Keys: Move the character up, down, left and right.
Earn Points: Move forward and reach new positions to increase your score.
Avoid Animals: Animals move across the screen in random directions. Colliding with one while not jumping causes you to lose a life.
Survive: Players have three lives. Once all three are lost, the game ends.

`def on_up_pressed():
    global highest_y
    if jumping == False:
        mySprite.y -= 20
        if mySprite.y < highest_y:
            highest_y = mySprite.y
            info.change_score_by(1)
controller.up.on_event(ControllerButtonEvent.PRESSED, on_up_pressed)

def on_a_pressed():
    global jumping, highest_y
    if jumping == False:
        jumping = True
        mySprite.y -= 20
        if mySprite.y < highest_y:
            highest_y = mySprite.y
            info.change_score_by(1)
        pause(200)
        jumping = False
controller.A.on_event(ControllerButtonEvent.PRESSED, on_a_pressed)

def on_left_pressed():
    if mySprite.x > 15:
        mySprite.x -= 10
controller.left.on_event(ControllerButtonEvent.PRESSED, on_left_pressed)

def on_right_pressed():
    if mySprite.x < 145:
        mySprite.x += 10
controller.right.on_event(ControllerButtonEvent.PRESSED, on_right_pressed)

def on_down_pressed():
    if jumping == False and mySprite.y < 110:
        mySprite.y += 20
controller.down.on_event(ControllerButtonEvent.PRESSED, on_down_pressed)

def on_on_overlap(player_sprite, obstacle):
    if jumping == False:
        info.change_life_by(-1)
        obstacle.destroy(effects.fire, 200)
        mySprite.x = 80
sprites.on_overlap(SpriteKind.player, SpriteKind.enemy, on_on_overlap)

def on_life_zero():
    game.over(False, effects.dissolve)
info.on_life_zero(on_life_zero)

direction = 0
animal: Sprite = None
jumping = False
highest_y = 0
mySprite: Sprite = None
game_speed = 35
highest_y = 110

    SpriteKind.player)
mySprite.x = 80
mySprite.y = 110
mySprite.z = 10
scene.camera_follow_sprite(mySprite)
game.splash("SAVANNAH DASH", "Crossy Road Adventure!")
game.show_long_text("Use arrow keys to move. Press A to jump. Avoid moving animals. Keep going to increase your score!",
    DialogLayout.CENTER)

def on_update_interval():
    global game_speed
    if game_speed < 90:
        game_speed += 5
game.on_update_interval(6000, on_update_interval)

def on_update_interval2():
    global animal, direction
    animal = sprites.create(img("""
           
        SpriteKind.enemy)
    # Animals appear ahead of the player
    animal.y = mySprite.y - randint(30, 100)
    direction = randint(0, 1)
    if direction == 0:
        animal.x = -10
        animal.vx = game_speed
    else:
        animal.x = 170
        animal.vx = 0 - game_speed
    animal.z = 5
game.on_update_interval(900, on_update_interval2)

def on_update_interval3():
    for obstacle2 in sprites.all_of_kind(SpriteKind.enemy):
        if obstacle2.y > mySprite.y + 150:
            obstacle2.destroy()
        if obstacle2.x < -30 or obstacle2.x > 190:
            obstacle2.destroy()
game.on_update_interval(500, on_update_interval3)
`


## Project Status
complete


## Room for Improvement
My game could be improved by giving the players a time limit. This would make my game more difficult which was what my peer feed back recommended. 


To do:
- Timer



## Acknowledgements
Give credit here.
- This project was inspired by Crossy Road
- This project was based on Crossy Road
- Many thanks to my Tutor and friends in class


## Contact
Created by [bella-rose.franklin@student.uts.edu.au) - feel free to contact me!

