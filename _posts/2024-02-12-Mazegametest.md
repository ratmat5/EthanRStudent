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
      destinationIndex: -1
    };

    function startGame() {
      const playerName = prompt("Enter your name:");
      if (!playerName) return;

      player.name = playerName;
      player.destinationIndex = -1;
      nextDestination();
    }

    function nextDestination() {
      player.destinationIndex++;
      if (player.destinationIndex >= destinations.length) {
        alert(`Congratulations, ${player.name}! You have completed your journey.`);
        return;
      }

      const destination = destinations[player.destinationIndex];
      const decision = confirm(`Welcome, ${player.name}! You have arrived at ${destination.name}. ${destination.description} Would you like to continue your journey?`);

      if (decision) {
        nextDestination();
      } else {
        alert(`Thank you for playing, ${player.name}! Your journey ends here.`);
      }
    }
  </script>
</body>
</html>
