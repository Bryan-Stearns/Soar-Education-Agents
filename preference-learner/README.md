# Preference Learner

You are making an agent that learns how to navigate a maze.

The agent is given direction choices on the input-link (up, down, left, right).
* Each choice comes with relevant information, like how much gold is in that direction

The agent starts with no knowledge of which direction to prefer.

The agent can ask its human helper to teach it which way to prefer between two options.

Goal: 
* The agent should learn rules that replicate the human’s navigation preferences.

## Excercise steps:

1. Modify the starting preflearn_main.soar file so that the agent sends a help request to the human helper when it has a tie impasse. Have it send a help request for a single pair of tied operators at a time. Then have the agent respond to input help by creating a 'better' preference between the two operators indicated in the input feedback.

