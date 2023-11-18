---
title: "Musical AI: Modeling Musical Counterpoint as a CSP"
date: 2018-12-19
cover: 
  image: "/ari-cover.png"
---



### What it is
Our team applied AI to music by working on modeling music composition as a Constraint Satisfaction Problem (CSP), building off previous research done into using CSPs to model counterpoint. 

#### More detail:
We produced a system that solves a given CSP according to the rules that we implemented to produce different compositions in MIDI format that we could listen to. We modeled compositions by setting rhythm to be 4/4 time (with random lengths of 1, 2, 3, or 4 quarter notes within those bars). Then we input a baseline or a "cantus firmus" as a list of notes. Our program added a simple 1-3-5-8 major chord on top of every note in the cantus firmus, then we used our solving algorithms to find melodies that satisfied the constraints we implemented to create one or more melodic lines on top.

For this project we implemented an Object-Oriented CSP and DFS, arc consistency, and simulated annealing algorithms as solving methods for that CSP.


### The fun stuff: Audio samples
We tested our algorithms' performance on randomly generated baselines, but here's an example of a solution MIDI that we generated given an input tune of "God is a Woman" by Ariana Grande for your listening pleasure:

![Ariana grande with a robot ooo](/ari.png)


<audio controls preload="metadata" style=" width:300px;">
	<source src="https://raw.githubusercontent.com/katherineqian/hosting/main/ariana.wav" type="audio/wav">
	Your browser does not support the audio element.
</audio><br />

More examples!

Shooting Star (DFS with arc consistency solution)
<audio controls preload="metadata" style=" width:300px;">
	<source src="https://raw.githubusercontent.com/katherineqian/hosting/main/shootingstar.wav" type="audio/wav">
	Your browser does not support the audio element.
</audio><br />

Shooting Star (simulated annealing solution)
<audio controls preload="metadata" style=" width:300px;">
	<source src="https://raw.githubusercontent.com/katherineqian/hosting/main/shootingstarsim.wav" type="audio/wav">
	Your browser does not support the audio element.
</audio><br />

Mary Had a Little Lamb (DFS with arc consistency solution)
<audio controls preload="metadata" style=" width:300px;">
	<source src="https://raw.githubusercontent.com/katherineqian/hosting/main/mary.wav" type="audio/wav">
	Your browser does not support the audio element.
</audio><br />


### Modeling counterpoint as constraints
We created a constraint graph with Variable and Constraint nodes and labeled Links (arcs) connecting them. The graph can be simplified by representing the Link-Constraint-Link relationships as a single arrow from Variable to Variable, or in this case note to note, to produce the following general setup for the graph structure used in this project:

![Diagram](/counterpoint-csp-graph.png)

As can be observed in the graph above, we imposed melodic constraints in the solved melody between each note and both of its neighbors, forward and backward. The melodic constraint ensures that in the solved melody, there is **no note jump greater than a minor 6th** and that **no interval is a tritone** (which is so dissonant that it has been nicknamed the ”devil’s interval”).

If you're curious, we concluded that DFS performs better in solving this OOP CSP than local search via simulated annealing using the metrics of run time, and that enforcing arc consistency improved the performance of both searches. We also saw that the success rate of simulated annealing was lower in every case except for the 4 bar compositions.


Find our project at https://github.com/gvashishtha/cs182_gjk.
