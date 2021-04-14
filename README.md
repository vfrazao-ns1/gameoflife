# Conway's Game of Life in x86

A simple implementation of Conway's Game of Life in x86_64 assembly.

## Requirements

* OS: Linux
* CPU architecture: amd64
* Terminal: xterm-256color

## Building

Simply run `make` and the binary will be built. No dependencies.

## Usage

The program takes two arguments passed through the commandline:

1. A grid or board, measuring 400 characters in length (representing a 20 by 20 grid) with live cells denoted by an 'X' and dead cells denoted by '.'
2. The number of generations to simulate (max val 2**63)

Each generation takes half a second of clock time.

Example GIF (quick note: asciinema didt quite capture the utf8 blocks well so they look distorted)

![Example 1](example.gif)

And another example:

![Example 2](example2.gif)

## Examples

An empty grid

```
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
....................
```

Would be invoked with:

```
./game_of_life ................................................................................................................................................................................................................................................................................................................................................................................................................ 50
```

Another grid:

```
....X...............
.....X..............
...XXX..............
....................
.............XXX....
....................
....................
....................
....X....X......X...
....X....X......X...
....X....X......X...
....................
....................
....................
....................
.....XXX............
.......X............
.....X...........XXX
.................X..
..................X.
```

Would be passed as:

```
./game_of_life ....X....................X.................XXX...............................................XXX....................................................................X....X......X.......X....X......X.......X....X......X........................................................................................XXX...................X.................X...........XXX.................X....................X. 50
```

And one more example:

```
.X...X.....XX...XXX.
..X.X.....X..X..X...
...X.......XX...XXXX
..X.X.....X..X..X..X
.X...X.....XX...XXXX
....................
....................
.....X....XXXX......
.....X....X.........
.....X....XXXX......
.....X.......X......
.....X....XXXX......
....................
....................
..XXXX.XXX.XXX.X....
..X....X.X.X.X.X....
..X....X.X.X.X.X....
..X....X.X.X.X.X....
..XXXX.XXX.XXX.XXXX.
....................
```

Would be:

```
./game_of_life
.X...X.....XX...XXX...X.X.....X..X..X......X.......XX...XXXX..X.X.....X..X..X..X.X...X.....XX...XXXX.............................................X....XXXX...........X....X..............X....XXXX...........X.......X...........X....XXXX................................................XXXX.XXX.XXX.X......X....X.X.X.X.X......X....X.X.X.X.X......X....X.X.X.X.X......XXXX.XXX.XXX.XXXX..................... 50
```
