#AI

Graph Attention Network

[Graph attention networks](https://scholar.google.com/scholar?oi=bibs&cluster=4768437242681188965&btnI=1&hl=en)
https://aisc.ai.science/static/slides/20190415_KarimKhayrat.pdf


Geometric Deep Learning
[Geometric deep learning: Grids, groups, graphs, geodesics, and gauges](https://scholar.google.com/scholar?oi=bibs&cluster=909412120305540598&btnI=1&hl=en)

TacticAI
https://deepmind.google/discover/blog/tacticai-ai-assistant-for-football-tactics/
https://www.nature.com/articles/s41467-024-45965-x
https://www.youtube.com/watch?v=I7J67JOkIbI


Hard to verify the suggestion useful

Predictive: Predict what will happen given a situation
Generative model: Generate some suggestion on tatical

Verify: Corner kick
Why not open play:
Too chaotic, situation can diverge extremely => Hard to follow a pre-suggested solution
even if you got a suggestion, cannot change tactic immediately

Corner kick:
Set piece => Same variables (10/match)
Occurs frequently + High xG => Important
Court symmetry => Can generalize data

can be validated with expert, coaches

Generalize motif < TacticAI (but close to sys1) < Model of the world (simulation)


Simulation helpful predict far to the future, corner kick based on local decision (~10s), simulation a game of football have too many human, chaotic factor => hard to predict, chance of a particular sequence happening is ~0 when predict far enough from the starting point => not practical

Potential (Future)
Near future: Set piece
Start from penalty, now cornerkick because the position of play is the same, near future can focus more on free kick, throw in (the position of play is not the same everytime, cannot control where the freekick , throw in happen => broader set of conditions to model from)

The more the rigid the problem , easier to modelize and predict

Far future: Open play but focus more on distributional pattern, eg: find some pattern of play on the field and suggest subtitiution to improve the situation

Team sport: Model relation between player with graph attention network, geometric deep learning to model the pitch => Can be generalize to multiple team sport (baseball, american football, basketball)

geometric deep learning, graph attention network: If the problem is natural, involes complex interactions (forecast weather, metarial structure)
Football: A complex natural problem which focuses a lot on relation between players, eg: synergies between teammate, anti-synergies with opponent player (eg: a player is good at defending a player, ...), can involves multiple player in a pattern (triangle play, ...) => Pattern can be model in a very structural way (node and graph) => gat and gdl can model this in a very principle way, with fixed ammount of computation per iteration => well suited for this class of problems

Corner kick: Snapshot at the time the ball being kicked, fixed graph, fixed number of message passing steps (~4 layer => helpful for shorterm model)

Potential (can extend layer to model more complex problem)

Generative model: A form of autoencoder => Not trained to produce (new) tactical suggestions, trained to reconstruct the initial tactics
Input: a new situation, and a shot flag to guide the AI either to 0: toward retrieve the ball and preserve control or 1: higher probability for the shot to happen, the model is setting to minimize the mean of error^2 => diverge subtle from the initial input to help the condition being set however, not really suggesting new tactics directly, more so the refinement of existing tactic.
Coach have to watch so many film to figure out what is benefical of harmful to a play and recognizing pattern in a play and think idea on how to refine (very hard to discover this factor) it which TacticAI is focus on: discovering and refining pattern based on what the user want => less time for coaches have to watch film and discover this themselves, the suggestions may not always be correct however can help the coaches recognize the problems of a play very fast and efficient => more time to training to refine the tactics