---
layout: base
title: Zaid Alrefai
description: Home Page
hide: true
image: /images/mario_animation.png
---



<html>
<head>
<style>
body {
  background-image: url('https://backend.artreview.com/wp-content/uploads/2022/03/heroDn3SrrTeZNNq5x62Rn4bhc-2048x1000.jpg');
  background-repeat: no-repeat;
  background-attachment: fixed; 
  background-size: 100% 100%;
}
</style>
</head>
<h1 style="font-family:Agmena;">Welcome to My Website</h1>
    <hr width="100%" size="5">
 
<h4 style="font-family:Agmena;"> I will be discussing my favorite games and games I am currently playing and giving my opinions on them.</h4>


<h4 style="font-family:Agmena;"> If you want to learn more about the current game I am playing, Black Myth Wukong, click below.</h4>
<br>
<div class="floatright">
<img align="right" 
         src=
"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQslo0rYXg8r4u6D5BVrqytQtEZvKbN_Viutw&s" 
         alt="BMWK Cover">


<head>
<style>
.button {
  background-color: #302f2f;
  border: 2px solid #2f5937;
  border-radius: 8px;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  transition-duration: 0.4s;
  margin: 4px 2px;
  cursor: pointer;
}


</style>
</head>
<body>

<div class="vertical-center">
<a href="https://blackmythwukong.fandom.com/wiki/Black_Myth:_Wukong_Wiki" class="button">Black Myth Wukong Wiki</a>
 </div>

</body>
<br>

<h4 style="font-family:Agmena;"> If you want to learn more about Elden Ring and dive deeper into the game, click below</h4>
<br>
<head>
<style>
.button {
  background-color: #302f2f;
  border: 2px solid #353736;
  border-radius: 8px;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  transition-duration: 0.4s;
  margin: 4px 2px;
  cursor: pointer;
}


</style>
</head>
<body>


<a href="https://eldenring.wiki.fextralife.com/Elden+Ring+Wiki" class="button">Elden Ring Wiki</a>


</body>


 <img align="right" 
         src=
"https://upload.wikimedia.org/wikipedia/en/b/b9/Elden_Ring_Box_art.jpg" 
         alt="Elden Ring Cover">


<head>
<style>
.button {
  background-color: #383131;
  border: 2px solid #2f5937;
  border-radius: 8px;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  transition-duration: 0.4s;
  margin: 4px 2px;
  cursor: pointer;
}


</style>
</head>
<body>

<div class="vertical-center">
<a href="https://eldenring.wiki.fextralife.com/Interactive+Map" class="button">Elden Ring Map</a>
 </div>

</body>

<br>
<h4 style="font-family:Agmena;">The wikis are excellent and were my main source for information on these games. They explain lore, show you where and how to get certain items, and where anything or anyone is located</h4>






<!--- Concatenation of site URL to frontmatter image  --->
{% assign sprite_file = site.baseurl | append: page.image %}
<!--- Has is a list variable containing mario metadata for sprite --->
{% assign hash = site.data.mario_metadata %}  
<!--- Size width/height of Sprit images --->
{% assign pixels = 256 %}

<!--- HTML for page contains <p> tag named "Mario" and class properties for a "sprite"  -->

<p id="mario" class="sprite"></p>
  
<!--- Embedded Cascading Style Sheet (CSS) rules, 
        define how HTML elements look 
--->
<style>

  /*CSS style rules for the id and class of the sprite...
  */
  .sprite {
    height: {{pixels}}px;
    width: {{pixels}}px;
    background-image: url('{{sprite_file}}');
    background-repeat: no-repeat;
  }

  /*background position of sprite element
  */
  #mario {
    background-position: calc({{animations[0].col}} * {{pixels}} * -1px) calc({{animations[0].row}} * {{pixels}}* -1px);
  }
</style>

<!--- Embedded executable code--->
<script>
  ////////// convert YML hash to javascript key:value objects /////////

  var mario_metadata = {}; //key, value object
  {% for key in hash %}  
  
  var key = "{{key | first}}"  //key
  var values = {} //values object
  values["row"] = {{key.row}}
  values["col"] = {{key.col}}
  values["frames"] = {{key.frames}}
  mario_metadata[key] = values; //key with values added

  {% endfor %}

  ////////// game object for player /////////

  class Mario {
    constructor(meta_data) {
      this.tID = null;  //capture setInterval() task ID
      this.positionX = 0;  // current position of sprite in X direction
      this.currentSpeed = 0;
      this.marioElement = document.getElementById("mario"); //HTML element of sprite
      this.pixels = {{pixels}}; //pixel offset of images in the sprite, set by liquid constant
      this.interval = 100; //animation time interval
      this.obj = meta_data;
      this.marioElement.style.position = "absolute";
    }

    animate(obj, speed) {
      let frame = 0;
      const row = obj.row * this.pixels;
      this.currentSpeed = speed;

      this.tID = setInterval(() => {
        const col = (frame + obj.col) * this.pixels;
        this.marioElement.style.backgroundPosition = `-${col}px -${row}px`;
        this.marioElement.style.left = `${this.positionX}px`;

        this.positionX += speed;
        frame = (frame + 1) % obj.frames;

        const viewportWidth = window.innerWidth;
        if (this.positionX > viewportWidth - this.pixels) {
          document.documentElement.scrollLeft = this.positionX - viewportWidth + this.pixels;
        }
      }, this.interval);
    }

    startWalking() {
      this.stopAnimate();
      this.animate(this.obj["Walk"], 3);
    }

    startRunning() {
      this.stopAnimate();
      this.animate(this.obj["Run1"], 6);
    }

    startPuffing() {
      this.stopAnimate();
      this.animate(this.obj["Puff"], 0);
    }

    startCheering() {
      this.stopAnimate();
      this.animate(this.obj["Cheer"], 0);
    }

    startFlipping() {
      this.stopAnimate();
      this.animate(this.obj["Flip"], 0);
    }

    startResting() {
      this.stopAnimate();
      this.animate(this.obj["Rest"], 0);
    }

    stopAnimate() {
      clearInterval(this.tID);
    }
  }

  const mario = new Mario(mario_metadata);

  ////////// event control /////////

  window.addEventListener("keydown", (event) => {
    if (event.key === "ArrowRight") {
      event.preventDefault();
      if (event.repeat) {
        mario.startCheering();
      } else {
        if (mario.currentSpeed === 0) {
          mario.startWalking();
        } else if (mario.currentSpeed === 3) {
          mario.startRunning();
        }
      }
    } else if (event.key === "ArrowLeft") {
      event.preventDefault();
      if (event.repeat) {
        mario.stopAnimate();
      } else {
        mario.startPuffing();
      }
    }
  });

  //touch events that enable animations
  window.addEventListener("touchstart", (event) => {
    event.preventDefault(); // prevent default browser action
    if (event.touches[0].clientX > window.innerWidth / 2) {
      // move right
      if (currentSpeed === 0) { // if at rest, go to walking
        mario.startWalking();
      } else if (currentSpeed === 3) { // if walking, go to running
        mario.startRunning();
      }
    } else {
      // move left
      mario.startPuffing();
    }
  });

  //stop animation on window blur
  window.addEventListener("blur", () => {
    mario.stopAnimate();
  });

  //start animation on window focus
  window.addEventListener("focus", () => {
     mario.startFlipping();
  });

  //start animation on page load or page refresh
  document.addEventListener("DOMContentLoaded", () => {
    // adjust sprite size for high pixel density devices
    const scale = window.devicePixelRatio;
    const sprite = document.querySelector(".sprite");
    sprite.style.transform = `scale(${0.2 * scale})`;
    mario.startResting();
  });

</script>

