---
toc: true
comments: true
layout: post
title: Test
description: Become one with your tools.  They could be more important than code, code, coding.
type: plans
courses: { csse: {week: 0}, csp: {week: 0, categories: [4.A]}, csa: {week: 0} }
categories: [C1.4]
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Travel Adventure</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }
    #game {
      margin-top: 20px;
    }
    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Travel Adventure</h1>
  <div id="game">
    <p>Welcome to the Travel Adventure Game!</p>
    <button onclick="startGame()">Start Journey</button>
  </div>

  <script>
    const destinations = [
      { name: "Beach", description: "Relax on the sandy beaches and enjoy the sun." },
      { name: "Mountain", description: "Embark on a hiking adventure and explore breathtaking views." },
      { name: "City", description: "Experience the vibrant culture and exciting nightlife of a bustling city." }
    ];

    let player = {
      name: "",
      destinationIndex: -1,
      health: 100,
      money: 100
    };

    function startGame() {
      const playerName = prompt("Enter your name:");
      if (!playerName) return;

      player.name = playerName;
      player.destinationIndex = -1;
      player.health = 100;
      player.money = 100;
      nextDestination();
    }

    function nextDestination() {
      player.destinationIndex++;
      if (player.destinationIndex >= destinations.length) {
        alert(`Congratulations, ${player.name}! You have completed your journey.`);
        return;
      }

      const destination = destinations[player.destinationIndex];
      const decision = confirm(`Welcome, ${player.name}! You have arrived at ${destination.name}. ${destination.description} Would you like to explore?`);

      if (decision) {
        exploreDestination(destination);
      } else {
        alert(`Thank you for playing, ${player.name}! Your journey ends here.`);
      }
    }

    function exploreDestination(destination) {
      const choice = prompt(`You are at ${destination.name}. What would you like to do?\n1. Relax\n2. Go sightseeing\n3. Try local cuisine\n4. Return to main menu`);
      if (!choice) return;

      switch (choice) {
        case "1":
          relax();
          break;
        case "2":
          goSightseeing();
          break;
        case "3":
          tryLocalCuisine();
          break;
        case "4":
          nextDestination();
          break;
        default:
          alert("Invalid choice. Please enter a number between 1 and 4.");
          exploreDestination(destination);
      }
    }

    function relax() {
      const relaxationLevel = Math.floor(Math.random() * 10) + 1;
      player.health += relaxationLevel;
      player.money -= 10;
      alert(`You spent some time relaxing. Your health increased by ${relaxationLevel}, but you spent $10.`);
      nextDestination();
    }

    function goSightseeing() {
      const sightseeingCost = 20;
      player.money -= sightseeingCost;
      const sightseeingResult = Math.random();
      if (sightseeingResult < 0.3) {
        player.health -= 20;
        alert("You had an accident while sightseeing and lost 20 health.");
      } else if (sightseeingResult < 0.6) {
        player.money += 30;
        alert("You found a valuable artifact while sightseeing and gained $30.");
      } else {
        player.health += 10;
        alert("You enjoyed sightseeing and gained 10 health.");
      }
      nextDestination();
    }

    function tryLocalCuisine() {
      const cuisineCost = 15;
      player.money -= cuisineCost;
      const cuisineResult = Math.random();
      if (cuisineResult < 0.4) {
        player.health -= 10;
        alert("You got food poisoning from the local cuisine and lost 10 health.");
      } else {
        player.health += 15;
        alert("You enjoyed the delicious local cuisine and gained 15 health.");
      }
      nextDestination();
    }
  </script>
</body>
</html>
