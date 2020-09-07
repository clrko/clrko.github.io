---
title: "Virtual Waiting Room"
excerpt: "A front-end web application developed during a remote hackathon with Doctolib, Dataiku and Wild Code School on the topic of remote healthcare."
header:
  image: /assets/images/virtual_waiting_room/first_prize.png
  teaser: assets/images/virtual_waiting_room/first_prize.png
order: 5
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

The [Travel Memory Game](https://travelmemorygame.netlify.app/) is a front-end web application developed on April 29th/30th during a 24h hackathon at Wild Code School on the topic of traveling from the couch. I was part of a 6-member team and we had only one requirement: using an api.   

We decided to design a game that a user in locked down would play in order to travel by seeing webcam videos of a country of his choice. In order to play, you first need to select a country and a category. Then, based on these two criteria, a memory game session will be generated. The objective is to find the 8 matching cards to win an access to the webcam of the chosen country. 

{% include gallery caption="These are some screenshot from the game" %}

For my team and I developing a game has been a good way to materialize what we had been learning during the first 2 months of the program, to consolidate our skills in React.js and learn how to use the hooks. 

In addition we have used 2 api :
* [Pixabay](https://pixabay.com/api/docs): we got from the api the images to be displayed in the game session based on 2 parameters: the country and the category (beach, nature etc.)
* [Windy](https://api.windy.com/webcams/docs): we got an access to a repository of webcams based on the country selected by the user. 

<div style="display:flex; justify-content:space-around; margin:30px 0;">
<img src="/assets/logo/HTML5_Logo.svg"  alt="HTML5 logo" style="width: 100px; height: auto;"/>
<img src="/assets/logo/CSS3_Logo.svg"  alt="CSS3 logo" style="width: 70px; height: auto;"/>
<img src="/assets/logo/JS_Logo.svg"  alt="JavaScript logo" style="width: 70px; height: auto;"/>
<img src="/assets/logo/Reactjs_Logo.svg"  alt="ReactJS logo" style="width: 90px; height: auto; grid-column: 2"/>
</div>

👉Play [here](https://travelmemorygame.netlify.app/) <br/>
👉Check the source code [here](https://github.com/clrko/travel_memory_game)