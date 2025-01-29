## COMP 122 Project Part 4 - Generative Music
*Create one or more Markov graphs to guide a sequence generator*

For the final stage in this project, we will define a "graph" for a Markov chain that will generate music according to probabilities defined by the composer (that's you). This is an algorithm found in many applications in which computers make decisions based on probability or observed patterns. 

In this project, the machine won't do any learning or adapting, though that might be the next extension if we were to develop this application further. Instead, you will construct a probability table that will govern the behavior of your system. It's a form of composition in which you set the parameters and let the process determine the actual result. The player application will generate a semi-random note sequence using your data file (markov.json) to choose the next note. Your file will define the probabilities of the transitions from one note to another as well as rhythmic values.

## Instructions

1. Use my handy Markov Music constructor form
* https://dbwetzel.github.io/COMP122-data-forms/markov.html

2. "Add Graph" to get started
3. Scroll down in the form to see the Pitch Set constructor. Add Nodes (pitch possibilities) and "Edge transitions" (possible next pitch for each pitch Node). Each time you update your graph, the player interface will update to reflect your changes. You can try it out in the constructor page.
4. Scroll down to the Rhythm Set. Vary the rhythm of your Matrix by adding new rhythmic possibilities for each duration Node. More instructions wil be avaiable in Sakai

Here's a possible Matrix:

``` 
[
  {
    "name": "Bass Line",
    "pitchSet": {
      "state": "C3",
      "matrix": {
        "C3": [
          "C3",
          "G2",
          "B2"
        ],
        "G2": [
          "G2",
          "C3"
        ],
        "B2": [
          "C3"
        ]
      }
    },
    "rhythmSet": {
      "state": "4n",
      "matrix": {
        "4n": [
          "4n",
          "8n"
        ],
        "8n": [
          "8n",
          "8n."
        ],
        "8n.": [
          "8n.",
          "8n",
          "8n.",
          "16n"
        ],
        "16n": [
          "16n",
          "16n",
          "4n"
        ]
      }
    }
  }
]
```
8. **Test your player.** You should see a colored circle (colors are random) with the name of each note node in your pitch set matrix. You should also see arrows indicating the possible connections from one note to the next. **Start the transport and press the play button** for your music generator. You should see and hear a Markov-generated note sequence. 
9. **Create a second music generator** as the second object in the top-level array. Maybe you want them to harmonize, and maybe you don't. You have total freedom in terms of what pitches and rhythms you choose. Have fun!


