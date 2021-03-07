# Turtle vs Hare

## Introduction
  This program explores a race between a Turtle and a Hare based off rules.
  
## Rules
  The rules are as followed based off *Deitel, P, Deitel, H. Intro to Python for Computer Science and Data Science. Pearson, 2020, page 92*

* Rule 1

* Rule 2
  

```
import random
import math

def turtle_move():

    move1=random.randrange(1,11)
    return move1

def hare_move():

    move2=random.randrange(1,11)
    return move2

turtle_pos=1
hare_pos=1

if turtle_pos==hare_pos:
    print('OUCH')
##else:
##    print(f'\r{"T"*turtle_pos} {"H"*hare_pos}', end='')


game_status = 'CONTINUE'
    
while game_status == 'CONTINUE':



    turte_step=turtle_move()
    hare_step=hare_move()

    if turte_step in (1, 2, 3, 4, 5):
        move_status='fast pod'
        turtle_pos+=3
    elif turte_step in (6,7):
        move_status='slip'
        turtle_pos-=6
    else:
        move_status='slow pod'
        turtle_pos+=1


    if hare_step in (1, 2):
        move_status='do not move'
        hare_pos+=0
    elif hare_step in (3, 4):
        move_status='big hop'
        hare_pos+=9
    elif hare_step==5:
        move_status='big slip'
        hare_pos-=12
    elif hare_step in (6,7,8):
        move_status='small hop'
        hare_pos+=1
    else:
        move_status='small slip'
        hare_pos-=2

    if turtle_pos<1:
        turtle_pos=1
    if hare_pos<1:
        hare_pos=1

    if turtle_pos==hare_pos:
        print(f'\r{"OUCH":>{turtle_pos}}', end='')
    elif turtle_pos>hare_pos:
        print(f'\r{"H":>{hare_pos}}{"T":>{turtle_pos-hare_pos}}', end='')
    else:
        print(f'\r{"T":>{turtle_pos}}{"H":>{hare_pos-turtle_pos}}', end='')


    if turtle_pos>=70 and hare_pos<70:
        game_status = 'TORTOISE WINS'
        print()
        print(game_status, end='\n')
##        print(turtle_pos)
##        print(hare_pos)
    elif hare_pos>=70 and turtle_pos<70:
        game_status = 'HARE WINS'
        print()
        print(game_status, end='\n')
##        print(turtle_pos)
##        print(hare_pos)
    elif hare_pos<=70 and turtle_pos<=70:
        game_status = 'CONTINUE'
##        print(game_status)
##        print(turtle_pos)
##        print(hare_pos)
    else:
        game_status = 'IT IS A TIE'
        print()
        print(game_status, end='\n')
##        print(turtle_pos)
##        print(hare_pos)
```
#### Listing 1. Turtle vs Hare Script

## Summary
  It is to be explored the win probability for each actor. As a follow up project, a simulation will be created to count the number of times each actor wins and estimate win probability.
