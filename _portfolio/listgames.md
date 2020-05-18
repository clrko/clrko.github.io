---
title: "Checkpoint 2 - List Games"
excerpt: "A responsive react app to display video game data."
header:
  image: /assets/images/checkpoint_list_games/landingpage.png
  teaser: assets/images/checkpoint_list_games/landingpage.png
order: 2
gallery:
  - url: /assets/images/checkpoint_list_games/landingpage.png
    image_path: assets/images/checkpoint_list_games/landingpage.png
    alt: "The landing page displaying the full list of games with their title and rating"
  - url: /assets/images/checkpoint_list_games/remove.png
    image_path: assets/images/checkpoint_list_games/remove.png
    alt: "Confirmation box that appear when the remove button is clicked"
  - url: /assets/images/checkpoint_list_games/screenshots.png
    image_path: assets/images/checkpoint_list_games/screenshots.png
    alt: "Display of the screenshots of a game"
---

The [List Games](https://listgames.netlify.app/) app has been developed during the second Wild Code School checkpoint on Front End development. 

I created a react app in which I use 2 components to display video game data from an API using axios. I decided to code using state Hooks. 

{% include gallery caption="These are some screenshot from the game" %}

The main features are the following:

- Using axios to fetch data from the <https://wild-games.herokuapp.com/api/v1> api;
- Button to remove a game on click;
- Button to filter the games by rating (breakpoint at 4.5);
- Screenshot page to display several images for a selected game.

<div style="display:flex; justify-content:space-around; margin:30px 0;">
<img src="/assets/logo/CSS3_Logo.svg"  alt="CSS3 logo" style="width: 70px; height: auto;"/>
<img src="/assets/logo/Reactjs_Logo.svg"  alt="ReactJS logo" style="width: 90px; height: auto;"/>
</div>

👉See [here](https://listgames.netlify.app/)<br/>
👉Check the source code [here](https://github.com/clrko/checkpoint_2_games)