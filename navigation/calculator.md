---
layout: post
title: Calculator
description: 
permalink: /javascript/project/simple-calculator
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
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .calculator {
    background-color: #333;
    border-radius: 10px;
    padding: 20px;
    width: 300px;
    box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.2);
  }

  .calculator-display {
    background-color: #111;
    color: #fff;
    font-size: 2em;
    text-align: right;
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 20px;
  }

  .calculator-keys {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }

  .calculator-key {
    background-color: #555;
    border: none;
    color: #fff;
    font-size: 1.5em;
    padding: 20px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .calculator-key:hover {
    background-color: #777;
  }

  .calculator-key.operator {
    background-color: #f39c12;
  }

  .calculator-key.operator:hover {
    background-color: #f1c40f;
  }

  .calculator-key.equal {
    background-color: #27ae60;
    grid-column: span 2;
  }

  .calculator-key.equal:hover {
    background-color: #2ecc71;
  }

  .calculator-key.clear {
    background-color: #e74c3c;
    grid-column: span 2;
  }

  .calculator-key.clear:hover {
    background-color: #e74c3c;
  }

</style>

<div class="calculator">
  <!-- Display -->
  <div class="calculator-display" id="calculator-display">0</div>

  <!-- Keys -->
  <div class="calculator-keys">
    <button class="calculator-key" data-action="number">7</button>
    <button class="calculator-key" data-action="number">8</button>
    <button class="calculator-key" data-action="number">9</button>
    <button class="calculator-key operator" data-action="operator">÷</button>

    <button class="calculator-key" data-action="number">4</button>
    <button class="calculator-key" data-action="number">5</button>
    <button class="calculator-key" data-action="number">6</button>
    <button class="calculator-key operator" data-action="operator">×</button>

    <button class="calculator-key" data-action="number">1</button>
    <button class="calculator-key" data-action="number">2</button>
    <button class="calculator-key" data-action="number">3</button>
    <button class="calculator-key operator" data-action="operator">−</button>

    <button class="calculator-key" data-action="number">0</button>
    <button class="calculator-key" data-action="number">.</button>
    <button class="calculator-key operator" data-action="operator">+</button>
    <button class="calculator-key equal" data-action="equal">=</button>

    <button class="calculator-key clear" data-action="clear">C</button>
  </div>
</div>

<script>
  (function() {
    // Calculator Elements
    const display = document.getElementById("calculator-display");
    const keys = document.querySelectorAll(".calculator-key");

    // Calculator State
    let currentValue = "0";
    let firstOperand = null;
    let operator = null;
    let waitingForSecondOperand = false;

    // Update the display
    function updateDisplay() {
      display.textContent = currentValue;
    }

    // Handle key press
    function handleKeyPress(key) {
      const action = key.dataset.action;
      const value = key.textContent;

      switch (action) {
        case "number":
          if (waitingForSecondOperand) {
            currentValue = value;
            waitingForSecondOperand = false;
          } else {
            currentValue = currentValue === "0" ? value : currentValue + value;
          }
          break;

        case "operator":
          if (firstOperand === null && !waitingForSecondOperand) {
            firstOperand = parseFloat(currentValue);
            operator = value;
            waitingForSecondOperand = true;
          } else if (!waitingForSecondOperand) {
            firstOperand = performCalculation(firstOperand, parseFloat(currentValue), operator);
            currentValue = String(firstOperand);
            operator = value;
            waitingForSecondOperand = true;
          }
          break;

        case "equal":
          if (firstOperand !== null && !waitingForSecondOperand) {
            currentValue = String(performCalculation(firstOperand, parseFloat(currentValue), operator));
            firstOperand = null;
            operator = null;
            waitingForSecondOperand = false;
          }
          break;

        case "clear":
          currentValue = "0";
          firstOperand = null;
          operator = null;
          waitingForSecondOperand = false;
          break;

        case ".":
          if (!currentValue.includes(".")) {
            currentValue += ".";
          }
          break;
      }

      updateDisplay();
    }

    // Perform the calculation based on the operator
    function performCalculation(first, second, operator) {
      switch (operator) {
        case "+":
          return first + second;
        case "−":
          return first - second;
        case "×":
          return first * second;
        case "÷":
          return first / second;
        default:
          return second;
      }
    }

    // Add event listeners to all calculator keys
    keys.forEach(function(key) {
      key.addEventListener("click", function() {
        handleKeyPress(key);
      });
    });

    // Initialize display
    updateDisplay();
  })();
</script>
