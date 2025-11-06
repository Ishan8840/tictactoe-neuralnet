# Tic-Tac-Toe AI with Neural Network 🤖🎮

Play Tic-Tac-Toe against an AI that learns optimal moves using a neural network trained on thousands of simulated games.

---

## Features

* **AI Training via Self-Play:** AI generates thousands of games to learn.
* **Neural Network:** PyTorch model predicts the best move given a board state.
* **Minimax Optimization:** Ensures optimal moves for AI during training.
* **Playable Game:** Human can play against AI in the terminal.
* **Save & Load Model:** Trained AI can be reused without retraining.

---

## Demo

```
Board positions: 0-8 (left to right, top to bottom)

 | | 
-----
 | | 
-----
 | | 

Your move (0-8): 0
AI moves to: 4

X| | 
-----
 |O| 
-----
 | | 

Your move (0-8): 1
AI moves to: 8

X|X| 
-----
 |O| 
-----
 | |O

...
AI wins! 🏆
```

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/Ishan8840/TicTacNN.git
cd tictactoe-ai
```

2. Install dependencies:

```bash
pip install torch numpy scikit-learn
```

---

## Usage

### 1️⃣ Generate Training Data

```bash
python generate_data.py
```

* Generates thousands of games for AI training.
* Saves `X.npy` (board states) and `y.npy` (optimal moves).

---

### 2️⃣ Train the Neural Network

```bash
python train_model.py
```

* Fully connected network: 9 → 128 → 128 → 9 neurons.
* Trains for 300 epochs.
* Outputs loss and accuracy every 10 epochs.
* Saves model as `tictac_model.pth`.

---

### 3️⃣ Play Against AI

```bash
python play_ai.py
```

* AI randomly decides whether it goes first.
* Enter moves as numbers `0-8`.
* Board updates after each move and announces the winner.

---

## File Structure

```
tictactoe-ai/
│
├── generate_data.py      # Generates training dataset
├── train_model.py        # Trains the neural network
├── play_ai.py            # Play against the trained AI
├── X.npy                 # Saved board states
├── y.npy                 # Saved moves
├── tictac_model.pth      # Trained AI model
└── README.md
```

---

## Neural Network Architecture

* **Input Layer:** 9 neurons (board state)
* **Hidden Layers:** 2 layers with 128 neurons each, ReLU activation
* **Output Layer:** 9 neurons (move probabilities)
* **Loss Function:** CrossEntropyLoss
* **Optimizer:** Adam

---

## How It Works

1. **Data Generation:**

   * AI plays against a random opponent.
   * Board states and AI moves are recorded using the minimax algorithm.
2. **Training:**

   * Neural network learns from board states to predict the best move.
3. **Gameplay:**

   * The AI evaluates the board and selects the move with the highest predicted score.

---

## Example Board State Encoding

| Board Cell  | Encoding |
| ----------- | -------- |
| AI (`X`)    | 1        |
| Human (`O`) | -1       |
| Empty       | 0        |

Example:

```
Board:  X |   | O
        ---------
           | X | 
        ---------
         |   | O

Encoded: [1,0,-1,0,1,0,0,0,-1]
```

---

## License

This project is licensed under the MIT License.

---


Do you want me to do that?
