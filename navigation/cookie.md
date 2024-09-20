---
layout: post
title: Cookie Clicker
description: 
permalink: /javascript/project/cookie-clicker
toc: true
comments: false
---

<style>
  /* Scrollable navbar styling */
  .navbar {
    display: flex;
    overflow-x: auto; /* Horizontal scroll */
    white-space: nowrap; /* Prevent wrapping */
    background-color: #333;
    padding: 10px;
    scrollbar-width: thin; /* Thin scrollbar for Firefox */
  }

  .navbar a {
    display: inline-block;
    color: white;
    text-align: center;
    padding: 14px 20px;
    text-decoration: none;
    font-size: 17px;
  }

  .navbar a:hover {
    background-color: #ddd;
    color: black;
  }

  .navbar::-webkit-scrollbar {
    display: none; /* Hide scrollbar for Chrome/Safari */
  }

  body {
    font-family: Arial, sans-serif;
  }

  .container {
    text-align: center;
    padding: 50px;
  }

  #cookie {
    width: 150px;
    height: 150px;
    background-image: url('https://preview.redd.it/gwfcuhc46ow71.png?width=470&format=png&auto=webp&s=95d7a769b67fe6991813a668be9414b8d92df1f2');
    background-size: cover;
    border: none;
    cursor: pointer;
  }

  #cookie:hover {
    transform: scale(1.1);
    transition: 0.1s;
  }

  .score {
    font-size: 24px;
    margin-top: 20px;
    color: #333;
  }

  .upgrade {
    margin-top: 20px;
    padding: 10px;
    background-color: #333;
    color: #fff;
    cursor: pointer;
    border: none;
    font-size: 18px;
  }

  .upgrade:hover {
    background-color: #555;
  }
</style>

<div class="container">
    <header class="pb-3 mb-4 border-bottom border-primary text-dark">
        <p class="fs-4">Cookie Clicker Score: <span id="score_value">0</span></p>
    </header>

    <!-- Cookie Image -->
    <button id="cookie"></button>

    <!-- Score Display -->
    <p class="score">Cookies: <span id="score">0</span></p>

    <!-- Upgrade Button -->
    <button id="upgrade" class="upgrade">Buy Auto Clicker (Cost: 100 Cookies)</button>
</div>

<script>
  (function() {
    // Initialize variables
    let score = 0;
    let cookiesPerClick = 1;
    let autoClickers = 0;
    let autoClickerCost = 100;

    // Elements
    const cookieButton = document.getElementById("cookie");
    const scoreDisplay = document.getElementById("score");
    const upgradeButton = document.getElementById("upgrade");

    // Click event for the cookie
    cookieButton.addEventListener("click", function() {
      score += cookiesPerClick;
      scoreDisplay.textContent = score;
    });

    // Upgrade button to buy auto-clickers
    upgradeButton.addEventListener("click", function() {
      if (score >= autoClickerCost) {
        score -= autoClickerCost;
        autoClickers += 1;
        autoClickerCost = Math.round(autoClickerCost * 1.15); // Increase the cost of the next auto-clicker
        upgradeButton.textContent = `Buy Auto Clicker (Cost: ${autoClickerCost} Cookies)`;
        scoreDisplay.textContent = score;
      }
    });

    // Auto-clicker function (clicks every second for each auto-clicker)
    setInterval(function() {
      score += autoClickers;
      scoreDisplay.textContent = score;
    }, 1000);
  })();
</script>
