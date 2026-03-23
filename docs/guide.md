# Game Development Guide with p5.js

## Getting Started with p5.js

1. Open `index.html` in a web browser to run the game
2. Edit `sketch.js` to modify the game code
3. Refresh the browser to see changes

## Project Structure

- `index.html`: Main HTML file that loads p5.js and your game
- `sketch.js`: Main game code using p5.js functions
- `assets/`: Images, sounds, fonts (add as needed)
- `docs/`: Documentation and guides

## Basic p5.js Structure

Every p5.js sketch needs:
1. `setup()`: Called once at the beginning
2. `draw()`: Called repeatedly (60 times per second by default)

## Key p5.js Functions

- `createCanvas(width, height)`: Create the drawing canvas
- `background(color)`: Set the background color
- `fill(color)`: Set the fill color for shapes
- `rect(x, y, width, height)`: Draw a rectangle
- `ellipse(x, y, width, height)`: Draw an ellipse/circle
- `keyIsDown(keyCode)`: Check if a key is pressed
- `createVector(x, y)`: Create a 2D vector

## Game Ideas

- Pong (sample provided)
- Snake
- Tetris
- Space Invaders
- Pac-Man
- Breakout
- Asteroids

## Collaboration Tips

- Use branches for new features
- Write clear commit messages
- Review each other's code
- Use issues to track tasks

## Resources

- [p5.js Reference](https://p5js.org/reference/)
- [p5.js Examples](https://p5js.org/examples/)
- [The Coding Train](https://thecodingtrain.com/) - Excellent tutorials
- [p5.js Web Editor](https://editor.p5js.org/) - Online editor for testing