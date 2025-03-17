# Chess AI

A fully-functional chess game with an intelligent computer opponent implemented in Python.

## Features

- Complete chess engine with all standard rules:
  - Castling (kingside and queenside)
  - En passant captures
  - Pawn promotion
  - Check, checkmate and stalemate detection
- Smart AI opponent using Negamax algorithm with Alpha-Beta pruning
- Interactive graphical interface built with Pygame
- Visual move highlighting and animations
- Move log display
- Undo move functionality

## Installation

1. Ensure you have Python 3.x installed
2. Install required dependencies:
   ```
   pip install pygame
   ```
3. Download or clone this repository
4. Place chess piece images in an 'images' folder with the following naming convention:
   - `wp.png` - white pawn
   - `wR.png` - white rook
   - `wN.png` - white knight
   - `wB.png` - white bishop
   - `wQ.png` - white queen
   - `wK.png` - white king
   - `bp.png` - black pawn
   - `bR.png` - black rook
   - `bN.png` - black knight
   - `bB.png` - black bishop
   - `bQ.png` - black queen
   - `bK.png` - black king

## Usage

Run the game by executing:
```
python ChessMain.py
```

### Controls

- **Mouse**: Click on a piece and then click on a valid destination square to move
- **Z key**: Undo the last move
- **R key**: Reset the game to the starting position

## Project Structure

- **ChessMain.py**: Main driver file that handles the game loop, UI rendering, and user input
- **ChessEngine.py**: Core chess logic including game state management, move validation, and rule implementation
- **ChessAI.py**: AI opponent implementation using Negamax with Alpha-Beta pruning

## AI Implementation

The AI uses the Negamax algorithm with Alpha-Beta pruning to search the game tree to a default depth of 4 moves. Position evaluation includes:

- Material balance (piece values: Queen=9, Rook=5, Bishop/Knight=3, Pawn=1)
- Piece positioning using piece-square tables (different values based on piece location)
- Special evaluation for checkmate and stalemate positions

## Technical Details

- Board representation: 8×8 2D list with two-character strings representing pieces
- First character represents piece color ('w' or 'b')
- Second character represents piece type ('R', 'N', 'B', 'Q', 'K', or 'p')
- Empty squares represented as "--"
- Move generation using legal move filtering based on pins and checks
- Multiprocessing for AI calculations to prevent UI freezing

## Configuration

You can modify the following parameters in the code:

- **AI Search Depth**: Change the `DEPTH` constant in ChessAI.py (higher values make the AI stronger but slower)
- **Player Controls**: Set `player_one` and `player_two` variables in the `main()` function to control which side(s) humans play

## Future Improvements

Potential enhancements include:
- Opening book implementation
- Difficulty settings
- Time controls
- Network play
- Custom position setup

## License

This project is available as open source under standard open source licenses.