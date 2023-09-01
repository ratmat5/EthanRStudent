---
toc: true
comments: true
layout: post
title: Guess The Number
description: Try and guess the number.
type: tangibles
courses: { csse: {week: 0}, csp: {week: 2, categories: [4.A]}, csa: {week: 0} }
categories: [C1.4]
---

<!DOCTYPE html>
<html>
<head>
    <title>Guess the Number Game</title>
</head>
<body>
    <h1>Guess the Number Game</h1>
    <p>Guess a number between 1 and 100:</p>
    <input type="number" id="guessInput">
    <input type="submit" value="Submit Guess" id="guessSubmit">
    <p id="message"></p>
    
    <script>
        // Generate a random number between 1 and 100
        const secretNumber = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        // Get references to the HTML elements
        const guessInput = document.getElementById("guessInput");
        const guessSubmit = document.getElementById("guessSubmit");
        const message = document.getElementById("message");

        // Function to check the user's guess
        function checkGuess() {
            const userGuess = parseInt(guessInput.value);
            attempts++;

            if (isNaN(userGuess) || userGuess < 1 || userGuess > 100) {
                message.textContent = "Please enter a valid number between 1 and 100.";
            } else if (userGuess < secretNumber) {
                message.textContent = "Too low! Try again.";
            } else if (userGuess > secretNumber) {
                message.textContent = "Too high! Try again.";
            } else {
                message.textContent = `Congratulations! You guessed the secret number ${secretNumber} in ${attempts} attempts.`;
                guessInput.disabled = true;
                guessSubmit.disabled = true;
            }
        }

        // Event listener for the submit button
        guessSubmit.addEventListener("click", checkGuess);

    </script>
</body>
</html>
