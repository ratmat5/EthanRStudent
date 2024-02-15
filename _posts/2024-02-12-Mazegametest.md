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
  <title>Whack-a-Mole</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 80vh;
    }
    .mole {
      width: 100px;
      height: 100px;
      background-color: brown;
      border-radius: 50%;
      position: relative;
    }
    .mole-hole {
      width: 120px;
      height: 120px;
      border: 2px solid black;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }
    .score {
      margin-top: 20px;
      font-size: 24px;
    }
  </style>
</head>
<body>
  <h1>Whack-a-Mole</h1>
  <div class="container">
    <div class="mole-hole" id="moleHole">
      <div class="mole" id="mole"></div>
    </div>
  </div>
  <div class="score" id="score">Score: 0</div>

  <script>
    let score = 0;
    const moleHole = document.getElementById('moleHole');
    const mole = document.getElementById('mole');
    const scoreDisplay = document.getElementById('score');

    moleHole.addEventListener('click', () => {
      if (mole.style.display !== 'none') {
        score++;
        scoreDisplay.textContent = `Score: ${score}`;
        mole.style.display = 'none';
      }
    });

    function moveMole() {
      const randomX = Math.random() * (window.innerWidth - 100);
      const randomY = Math.random() * (window.innerHeight - 100);
      mole.style.left = `${randomX}px`;
      mole.style.top = `${randomY}px`;
      mole.style.display = 'block';
    }

    setInterval(moveMole, 1000);
  </script>
</body>
</html>
