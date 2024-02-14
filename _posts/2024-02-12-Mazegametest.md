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
  <title>Language Guessing Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }
    #question {
      font-size: 24px;
      margin-bottom: 20px;
    }
    #options {
      display: flex;
      justify-content: center;
      gap: 10px;
      margin-bottom: 20px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Language Guessing Quiz</h1>
  <div id="question"></div>
  <div id="options"></div>
  <button id="nextButton" style="display: none;" onclick="nextQuestion()">Next Question</button>

  <audio id="audio" controls style="display: none;"></audio>

  <script>
    const questions = [
      {
        audioSrc: "audio/english.mp3",
        options: ["English", "Spanish", "French", "German"],
        answer: "English"
      },
      {
        audioSrc: "audio/spanish.mp3",
        options: ["French", "Arabic", "Spanish", "Italian"],
        answer: "Spanish"
      },
      {
        audioSrc: "audio/french.mp3",
        options: ["German", "Chinese", "Russian", "French"],
        answer: "French"
      },
      {
        audioSrc: "audio/german.mp3",
        options: ["Japanese", "German", "Korean", "Dutch"],
        answer: "German"
      },
      {
        audioSrc: "audio/italian.mp3",
        options: ["Italian", "Portuguese", "Swedish", "Turkish"],
        answer: "Italian"
      }
    ];

    let currentQuestionIndex = 0;
    let score = 0;

    function displayQuestion() {
      const currentQuestion = questions[currentQuestionIndex];
      document.getElementById("question").textContent = "Guess the language:";
      document.getElementById("audio").src = currentQuestion.audioSrc;

      const optionsDiv = document.getElementById("options");
      optionsDiv.innerHTML = "";
      currentQuestion.options.forEach(option => {
        const button = document.createElement("button");
        button.textContent = option;
        button.onclick = function() { checkAnswer(option); };
        optionsDiv.appendChild(button);
      });

      document.getElementById("nextButton").style.display = "none";
    }

    function checkAnswer(selectedOption) {
      const currentQuestion = questions[currentQuestionIndex];
      if (selectedOption === currentQuestion.answer) {
        alert("Correct!");
        score++;
      } else {
        alert("Incorrect! The correct answer is: " + currentQuestion.answer);
      }

      currentQuestionIndex++;
      if (currentQuestionIndex < questions.length) {
        displayQuestion();
      } else {
        endGame();
      }
    }

    function endGame() {
      alert("Quiz finished! Your score: " + score + "/" + questions.length);
      document.getElementById("nextButton").style.display = "none";
    }

    function nextQuestion() {
      displayQuestion();
    }

    displayQuestion();
  </script>
</body>
</html>
