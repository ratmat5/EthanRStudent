---
toc: true
comments: true
layout: post
title: Tools Setup
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
  <title>Maze Adventure</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }
    #game {
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Maze Adventure</h1>
  <div id="game">
    <p>Welcome to the Maze Adventure Game!</p>
    <p>Enter your name: <input type="text" id="playerName"></p>
    <button onclick="startGame()">Start Game</button>
  </div>

  <script>
    let player = {
      name: "",
      health: 100,
      position: { x: 0, y: 0 }
    };

    let mazeSize = 5; // Size of the maze (5x5 grid)
    let treasurePosition = { x: 0, y: 0 };
    let trapPositions = [];

    function generateMaze() {
      treasurePosition = {
        x: Math.floor(Math.random() * mazeSize),
        y: Math.floor(Math.random() * mazeSize)
      };

      for (let i = 0; i < mazeSize; i++) {
        trapPositions.push({
          x: Math.floor(Math.random() * mazeSize),
          y: Math.floor(Math.random() * mazeSize)
        });
      }
    }

    function startGame() {
      const playerName = document.getElementById("playerName").value;
      if (playerName.trim() === "") {
        alert("Please enter your name.");
        return;
      }

      player.name = playerName;
      generateMaze();
      renderGame();
    }

    function move(direction) {
      switch (direction) {
        case "up":
          player.position.y++;
          break;
        case "down":
          player.position.y--;
          break;
        case "left":
          player.position.x--;
          break;
        case "right":
          player.position.x++;
          break;
      }

      checkGameState();
      renderGame();
    }

    function checkGameState() {
      if (player.position.x === treasurePosition.x && player.position.y === treasurePosition.y) {
        alert(`Congratulations, ${player.name}! You found the treasure and won the game!`);
        resetGame();
      }

      for (const trap of trapPositions) {
        if (player.position.x === trap.x && player.position.y === trap.y) {
          const damage = Math.floor(Math.random() * 20) + 10;
          player.health -= damage;
          alert(`Oh no, you stepped on a trap and lost ${damage} health!`);
          if (player.health <= 0) {
            alert(`Game over, ${player.name}! Your health reached zero.`);
            resetGame();
          }
          break;
        }
      }
    }

    function renderGame() {
      const gameDiv = document.getElementById("game");
      gameDiv.innerHTML = `
        <p>Hello, ${player.name}! You are at position (${player.position.x}, ${player.position.y}).</p>
        <p>Health: ${player.health}</p>
        <p>Use the arrow keys to move:</p>
        <button onclick="move('up')">Up</button>
        <button onclick="move('down')">Down</button>
        <button onclick="move('left')">Left</button>
        <button onclick="move('right')">Right</button>
      `;
    }

    function resetGame() {
      player.health = 100;
      player.position = { x: 0, y: 0 };
      trapPositions = [];
      generateMaze();
      renderGame();
    }
  </script>
</body>
</html>
