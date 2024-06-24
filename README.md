# PacmanAI Project

The **PacmanAI Project** is a Python-based application that uses reinforcement learning with feature extraction to enhance Pacman's gameplay. This assignment was design at berkeley for educational purposes and demonstrates the development of a sophisticated feature extractor for Pacman to maximize its score, utilizing various AI and machine learning techniques.

Licensing Information:  You are free to use or extend these projects for
educational purposes provided that you retain this notice, and you provide clear
attribution to UC Berkeley, including a link to http://ai.berkeley.edu.

Attribution Information: The Pacman AI projects were developed at UC Berkeley.
The core projects and autograders were primarily created by John DeNero
(denero@cs.berkeley.edu) and Dan Klein (klein@cs.berkeley.edu).
Student side autograding was added by Brad Miller, Nick Hay, and
Pieter Abbeel (pabbeel@cs.berkeley.edu).

## Introduction

The aim of this project is to develop a sophisticated feature extractor for Pacman, enabling it to learn and improve its gameplay through reinforcement learning. By reducing the complexity of the game state to a simpler representation, Pacman can effectively use Q-learning techniques to maximize its score.

## Requirements

The project requires Python, graphics are implemented in a few graphics python file

## Installation

Follow these steps to install and set up the project:

### 1. Clone the Repository
`git clone https://github.com/KyleNewbigging/PacmanAI.git`

### 2. Navigate to the Project Directory
`cd PacmanAI`


## Execution
1. Run the game and play it using WASD, or Arrow keys:
`python pacman.py`
   
2. Run the existing SimpleExtractor and train Pacman through Q Learning
   Note: To see all command-line option see below this section
`python pacman.py -p ApproximateQAgent -a extractor=SimpleExtractor -x 50 -n 60 -l mediumGrid`

3. Run the Custom Feature Extractor

`python pacman.py -p ApproximateQAgent -a extractor=myExtractor -x 50 -n 60 -l mediumGrid`
`python pacman.py -p ApproximateQAgent -a extractor=myExtractor -x 50 -n 60 -l mediumClassic`
`python3 pacman.py -p ApproximateQAgent -a extractor=myExtractor -x 50 -n 60 -l myLayout`

## Command-Line Options for pacman.py

Below are the available command-line options for running `pacman.py` along with their descriptions and default values:

| Option                    | Description                                                             | Default           |
|---------------------------|-------------------------------------------------------------------------|-------------------|
| `-n, --numGames`          | The number of games to play                                             | 1                 |
| `-l, --layout`            | The layout file from which to load the map layout                       | mediumClassic     |
| `-p, --pacman`            | The agent type in the pacmanAgents module to use                        | KeyboardAgent     |
| `-t, --textGraphics`      | Display output as text only                                             | False             |
| `-q, --quietTextGraphics` | Generate minimal output and no graphics                                 | False             |
| `-g, --ghosts`            | The ghost agent type in the ghostAgents module to use                   | RandomGhost       |
| `-k, --numghosts`         | The maximum number of ghosts to use                                     | 4                 |
| `-z, --zoom`              | Zoom the size of the graphics window                                    | 1.0               |
| `-f, --fixRandomSeed`     | Fixes the random seed to always play the same game                      | False             |
| `-r, --recordActions`     | Writes game histories to a file (named by the time they were played)    | False             |
| `--replay`                | A recorded game file (pickle) to replay                                 | None              |
| `-a, --agentArgs`         | Comma separated values sent to agent. e.g. "opt1=val1,opt2,opt3=val3"   | None              |
| `-x, --numTraining`       | How many episodes are training (suppresses output)                      | 0                 |
| `--frameTime`             | Time to delay between frames; <0 means keyboard                         | 0.1               |
| `-c, --catchExceptions`   | Turns on exception handling and timeouts during games                   | False             |
| `--timeout`               | Maximum length of time an agent can spend computing in a single game    | 30                |

## Features Implemented
### Closest Capsule or Power Pellet:
Pacman tends to avoid these otherwise, so this feature encourages Pacman to prioritize capsules.

### Closest Scared Ghost:
Allows Pacman to determine if pursuing a scared ghost is beneficial, considering the scared timer and distance.

### Closest Food:
Modified to consider only ghosts that are not scared to ensure Pacman collects food efficiently.

## Average Scores
mediumGrid: 528.0
mediumClassic: 1457.5

## Custom Layout
I created a custom layout named mylayout.lay and it has been designed to benefit my feature extractor. 

### The layout has the following characteristics:
Contains 4 ghosts in a small area with more power pellets than typical layouts.
This results in higher scores due to the SimpleExtractor not considering scared ghosts effectively.

### Performance on Custom Layout:
myExtractor: 1835.0
SimpleExtractor: 1743.0
