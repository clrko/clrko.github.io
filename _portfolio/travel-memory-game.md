---
title: "Travel Memory Game"
excerpt: "An amazing app to play when you are locked down !"
header:
  image: /assets/images/travel_memory_game/travel_memory_game_homepage.png
  teaser: assets/images/travel_memory_game/travel_memory_game_homepage.png
gallery:
  - url: /assets/images/travel_memory_game/travel_memory_game_homepage.png
    image_path: assets/images/travel_memory_game/travel_memory_game_homepage.png
    alt: "Homepage"
  - url: /assets/images/travel_memory_game/travel_memory_game_gamesession.png
    image_path: assets/images/travel_memory_game/travel_memory_game_gamesession.png
    alt: "Game session"
  - url: /assets/images/travel_memory_game/travel_memory_game_webcam.png
    image_path: assets/images/travel_memory_game/travel_memory_game_webcam.png
    alt: "Webcam view"
---

The [Travel Memory Game](https://travel-memory-game.netlify.app/) is a front-end web application developed on April 29th/30th during a 24h hackathon at Wild Code School on the topic of travelling from the couch. I was part of a 6-member team and we had only one requirement: using an api.   

We decided to design a game that a user in locked down would play in order to travel by seeing webcam videos of a country of his choice. In order to play, you first need to select a country and a category. Then, based on these two criteria, a memory game session will be generated. The objective is to find the 8 matching cards to win an access to the webcam of the chosen country. 

{% include gallery caption="These are some screenshot from the game" %}

For my team and I developing a game has been a good way to materialize what we had been learning during the first 2 months of the program, to consolidate our skills in React.js and learn how to use the hooks. 

We have used 2 api :
* [Pixabay](https://pixabay.com/api/): we got from the api the images to be displayed in the game session based on 2 parameters: the country and the category (beach, nature etc.)
* [Windy](https://api.windy.com/webcams/docs): we got an access to a repository of webcams based on the country selected by the user. 

 👉https://travel-memory-game.netlify.app/