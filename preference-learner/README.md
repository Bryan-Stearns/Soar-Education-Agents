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
2. Chunking first steps. 
    1. Step back for an explanation about how chunking works. (TODO: Create materials. Read the old tutorial for now.) The WMEs tested in substate rules shape the conditions in the created chunk.
    2. Turn on chunking in your agent. See what happens after 3 decision cycles. The agent learned 2 chunks. (Type `print -fc` to see them) One of them recreates the result of (get-help), the other recreates the elaboration rule that applies the feedback from the input-link to create a preference. 
        1. We want the latter type but not the former. The former result of asking for help depends on the existence of an impasse. If there's no tie impasse, there's no need to ask for help. So we shouldn't actually learn a chunk for this result. Soar lets us indicate that a result depends on the impasse itself as a condition. We do that by testing the `quiesence t` structure in the substate. Add this condition to the (get-help) apply rule. This will tell Soar not to chunk that result.
        2. The other chunk is the right kind but it relies on the input-link feedback and doesn't let the agent behave on its own. More on that next lesson.
