---
title: "Realtime Score Prediction in ODI Cricket"
layout: project
---

> Course: AI3011: Machine Learning and Pattern Recognition
> Teammates: [Arnav Kapoor](https://www.linkedin.com/in/arnav-kapoor-9361a3112/), [Avantika Bansal](https://www.linkedin.com/in/avantika-bansal-9253b3278/), [Suraj Dayma](/)

* **[Code](https://github.com/S-rg/CricketFinalScorePrediction)** | **[Presentation](https://ai3011.plaksha.edu.in/Spring%202025/PDFs/Arnav%20Kapoor.pdf)** *

Cricket is a sport which generates a lot of statistical data. Metrics like runs, shot and ball type, and length are recorded for every over and are usually averaged to communicate the efficacy of players. Teams often use these metrics to curate their lineup of 11 players as well as decide which bowler to play against particular batsmen. Such analysis is aided by using machine learning techniques to predict the outcome of matches.

Current implementations of cricket predictive systems are severely limited in their scope. They fail to properly contextualize matchups and game states, alongside player styles and tendencies. Holistically modelling the effect of these factors on the decisions that batsmen and bowlers make will provide a comprehensive understanding of how to optimize bowling plans and strategies, alongside providing a deeper understanding of the game.

To implement this, we created spin factor and pace factor, which are metrics to quantify the pitch conditions. We are also using ball by ball data in One Day International matches from the past 2 decades. We are using a Long Short Term Memory (LSTM) model in order to predict the final score from a given game state. Ultimately, this system represents a more all-encompassing solution to analyzing and predicting team performances from a variety of game states.