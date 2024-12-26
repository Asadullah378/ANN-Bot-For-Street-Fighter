# Street Fighter Neural Network Bot

This repository contains a neural network-powered bot for playing the classic **Street Fighter** game. The bot leverages machine learning to predict optimal button inputs based on the game state, providing competitive gameplay for player-vs-bot matches.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [File Descriptions](#file-descriptions)
- [License](#license)

---

## Overview

The project is composed of two primary components:
1. **Model Training**: Uses historical game data to train a neural network to predict button inputs based on player positions and game states.
2. **Bot Controller**: Implements the trained model to simulate gameplay by dynamically adjusting button presses during a match.

---

## Features

- **Data-Driven Gameplay**: Utilizes machine learning to analyze game state and predict effective moves.
- **Scalable Architecture**: Easily adaptable to new datasets or game variations.
- **Interactive Bot**: Functions as a second player in a real-time match.

---

## Installation

### Prerequisites
Ensure you have the following installed:
- Python 3.8+
- TensorFlow
- Scikit-learn
- Joblib
- Pandas
- Numpy

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/street-fighter-bot.git
   cd street-fighter-bot
   ```
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Place your game data files (`GameData.csv` and optionally `NewGameData.csv`) in the project directory.

---

## Usage

### Training the Model
1. Run the training script to train the bot:
   ```bash
   python model.py
   ```
2. This generates two files:
   - `BotModel.h5`: The trained neural network model.
   - `scaler.save`: A scaler for input normalization.

### Running the Bot
1. Start the bot controller:
   ```bash
   python bot.py
   ```
2. The bot will interact with the game using the trained model to simulate player actions.

---

## How It Works

1. **Data Preprocessing**:
   - Game data is loaded and processed to extract relevant features.
   - Input features (e.g., player positions) are normalized using a scaler.

2. **Model Architecture**:
   - A simple feedforward neural network with two hidden layers is implemented using TensorFlow.
   - Outputs are button states (`True`/`False`) for various actions (e.g., `up`, `down`, `attack`).

3. **Real-Time Predictions**:
   - During gameplay, the bot receives the current game state, normalizes inputs, and uses the model to predict button presses.
   - Predicted actions are mapped to game commands, enabling dynamic gameplay.

---

## File Descriptions

- `model.py`: Script to train the neural network model using historical game data.
- `bot.py`: Implements the trained model to predict actions and interact with the game in real time.
- `GameData.csv`: Example dataset for training the model.
- `scaler.save`: Saved scaler for normalizing inputs during gameplay.
- `BotModel.h5`: Trained model file for predictions.

---

## License

This project is licensed under the MIT License. See the [License](License) file for details.
