---
layout: post
title: "Project Showcase 1: tetris-ai"
visible: false
---

This is the first part of a series on projects made by me. Some of them are finished, some are not, others may never even see the light of day. 

This first one is pretty self-explanatory, it's a game of Tetris, played by an AI. Everything is implemented in python using three libraries:
 - numpy
 - neat-python
 - pygame

## The game part

When I started working on this on thing, the first thing I did was make a playable version of Tetris. The game has two basic components: the `Mino` class and the `Game` class.

Let's start with `Mino`. It's used to represent a game piece and has somewhat basic properties:

```python3
class Mino:
    def __init__(self, type_: str, pos: Tuple[int, int] = None) -> None:
        if type_ not in 'IJLOSTZ':
            raise ValueError(f'invalid tetromino type {repr(type_)}')
        self.type = type_
        if pos is None:
            pos = SPAWN_POSITIONS[type_]
        self.x: int = pos[0]
        self.y: int = pos[1]
        self.direction = 'up'
        self.pos_log = [('', tuple(self.pos()), self.direction)]
```

As you can see, we only store what the piece is (`self.type`) , where it is (`self.x, self.y`), and its direction (`self.direction`). The `self.pos_log` here doesn't do much right now.

The real magic happens in the methods:

```python3
def render(self):
def rotate(self) -> None:
def check_collision(self, board, dirx=0, diry=1):
def move(self, board, dir_):
```

The `render` method takes predefined list of points corresponding to the piece and applies the relevant translations and rotations. Each piece has a rotation origin, and they're not all the same. If you don't respect this rotation origin, you might end up with the I piece swinging, for example.


`rotate` rotates the piece 90 degrees clockwise.

Now onto `check_collision`. This stores the rendered piece and checks the piece tiles against the board tiles offset by `(dirx, diry)`. If any tile is occupied, return `True`; otherwise return `False`. It also checks if the offset tiles are within bounds (`0 <= x < 10 and 0 <= y < 40`).

Finally, `move`:
```python3
...
        if dir_ == 'left':
            if not self.check_collision(board, -1, 0):
                self.x += -1
            return False
...
        elif dir_ == 'drop':
            while not self.check_collision(board, 0, 1):
                self.y += 1
            return True
        elif dir_ == 'nop':
            pass
...
```

It takes in an action (`'left', 'right', 'rotate', 'down',  'drop', 'nop'`)  and the game board. If the action is to move side to side, check collision in that direction and move if clear; it then returns `False`. 

`'rotate'` makes a copy of the piece, rotates it, and check the collision in place. In place here means checking if the piece currently collides with anything. It also returns `False`.

If the action is `'drop'`, keep moving the piece down until it collides with something, return `True` afterwards. A `'nop'` is just "do nothing".

The return value for this method tells the `Game` class whether or not to "paste" the piece onto board. Or in other words, make the piece tiles into board tiles. 



Now the `Game` class. This one has a lot more bits and pieces so I'll try to be as brief as possibe.

This class can be divided into four "chunks" thatt each have a job:

 - Gameplay
 - Self play
 - Timing
 - Rendering

#### Gameplay

This part handles things need to play the game, everything from generating a steady stream of pieces to moving them. It can be summarized into these methods:

```python3
def generate_minos():
def game_step(self, cmd='nop'):
def pop_from_bag(self, hold=False):
def hold(sel, ):
def paste_to_board(self ):
```

`generate_minos()` is a static method that returns a randomized permutation of `Mino()` objects.

`game_step(self, cmd='nop')` does the following sequence of events:
 - Make sure the command (`cmd`) is valid
 - If a command isn't being executed and rendering is enabled, render the board
 - If the command is `'gravity'`
   - 