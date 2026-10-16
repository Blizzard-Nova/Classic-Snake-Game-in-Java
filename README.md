# Classic Snake Game in Java

The classic Snake game re-created in Java using Swing and AWT. Steer the snake around the board, eat the food to grow, and avoid hitting the walls or your own tail.

## Features

- Grid-based gameplay on a 600×600 board (24×24 tiles of 25 px)
- Arrow-key controls
- Snake grows each time it eats food, which appears at a random tile
- Live score display, which turns into a "Game Over" banner with your final score
- Reverse-direction protection, so the snake can't turn straight back into itself
- No external dependencies, only the Java standard library

## Requirements

- Java Development Kit (JDK) 8 or newer to compile from source
- Java Runtime Environment (JRE) 8 or newer to run the prebuilt JAR

Check your installation with:

```bash
java -version
```

## Getting Started

### Clone the repository

```bash
git clone https://github.com/Blizzard-Nova/Classic-Snake-Game-in-Java.git
cd Classic-Snake-Game-in-Java
```

### Option 1: Run the prebuilt JAR

```bash
java -jar Snake.jar
```

### Option 2: Compile and run from source

```bash
javac App.java SnakeGame.java
java App
```

## How to Play

| Key | Action |
| --- | ------ |
| ↑ | Move up |
| ↓ | Move down |
| ← | Move left |
| → | Move right |

1. The snake starts standing still. Press any arrow key to start moving.
2. Guide the snake's head (blue) onto the food (red) to eat it and grow longer.
3. Each piece of food adds 2 points to your score, shown in the top-left corner.
4. The game ends if the snake hits a wall or runs into its own body.

## Project Structure

```
Classic-Snake-Game-in-Java/
├── App.java        # Entry point: creates the window and launches the game
├── SnakeGame.java  # Game logic, rendering, and keyboard input
├── Snake.jar       # Prebuilt, runnable version of the game
└── README.md
```

### How it works

- **`App.java`** sets up a non-resizable, centered `JFrame` with a 600×600 board and adds the game panel to it.
- **`SnakeGame.java`** extends `JPanel` and implements `ActionListener` and `KeyListener`.
  - A Swing `Timer` ticks every 100 ms. Each tick moves the snake, checks for collisions, and repaints the board.
  - The snake is a head `Tile` plus an `ArrayList<Tile>` for its body. Each body segment follows the one in front of it.
  - Food is placed on a random tile whenever the previous piece is eaten.

## Configuration

A few values are easy to tweak in the source:

| Setting | Location | Default |
| ------- | -------- | ------- |
| Board size | `boardWidth` in `App.java` | `600` |
| Tile size | `tileSize` in `SnakeGame.java` | `25` |
| Game speed | `new Timer(100, this)` in `SnakeGame.java` | `100` ms per move |
| Points per food | Score calculation in `draw()` | `2` |

## Possible Improvements

Ideas for anyone who wants to extend the project:

- Add a restart key after game over
- Keep a high score across sessions
- Prevent food from spawning on top of the snake
- Increase speed as the score grows
- Add a start screen and pause function

## Contributing

Contributions, issues, and feature requests are welcome. Feel free to fork the repository and open a pull request.

## License

No license has been specified for this project yet. Consider adding one, such as [MIT](https://choosealicense.com/licenses/mit/), if you'd like others to be able to reuse the code.
