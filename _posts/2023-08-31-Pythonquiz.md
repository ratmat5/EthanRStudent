---
toc: true
comments: false
layout: post
title: Python Quiz
description: Test your knowledge
type: tangibles
courses: { csse: {week: 0}, csp: {week: 2, categories: [4.A]}, csa: {week: 0} }
categories: [C1.4]
---

<!DOCTYPE html>
<html>
<head>
    <title>Simple Quiz</title>
</head>
<body>
    <h1>Simple Quiz</h1>
    <form id="quiz-form">
        <fieldset>
            <legend>Question 1: What is the capital of France?</legend>
            <label><input type="radio" name="q1" value="a">Paris</label><br>
            <label><input type="radio" name="q1" value="b">London</label><br>
            <label><input type="radio" name="q1" value="c">Berlin</label><br>
        </fieldset>
        <fieldset>
            <legend>Question 2: How many continents are there?</legend>
            <label><input type="radio" name="q2" value="a">5</label><br>
            <label><input type="radio" name="q2" value="b">6</label><br>
            <label><input type="radio" name="q2" value="c">7</label><br>
        </fieldset>
        <fieldset>
            <legend>Question 3: What gas do plants use for photosynthesis?</legend>
            <label><input type="radio" name="q3" value="a">Carbon dioxide</label><br>
            <label><input type="radio" name="q3" value="b">Oxygen</label><br>
            <label><input type="radio" name="q3" value="c">Nitrogen</label><br>
        </fieldset>
        <fieldset>
            <legend>Question 4: What does HTML stand for?</legend>
            <label><input type="radio" name="q4" value="a">Hyper Text Markup Language</label><br>
            <label><input type="radio" name="q4" value="b">High Tech Modern Language</label><br>
            <label><input type="radio" name="q4" value="c">Hot Tamale Microwave Lingo</label><br>
        </fieldset>
        <fieldset>
            <legend>Question 5: What is the largest planet in our solar system?</legend>
            <label><input type="radio" name="q5" value="a">Mars</label><br>
            <label><input type="radio" name="q5" value="b">Jupiter</label><br>
            <label><input type="radio" name="q5" value="c">Earth</label><br>
        </fieldset>
        <button type="button" id="submit-button">Submit Answers</button>
    </form>
    <div id="result"></div>
    <script>
        document.getElementById("submit-button").addEventListener("click", function() {
            const answers = {
                q1: document.querySelector('input[name="q1"]:checked'),
                q2: document.querySelector('input[name="q2"]:checked'),
                q3: document.querySelector('input[name="q3"]:checked'),
                q4: document.querySelector('input[name="q4"]:checked'),
                q5: document.querySelector('input[name="q5"]:checked')
            };
            let correctCount = 0;
            for (const question in answers) {
                if (answers[question] && answers[question].value === "a") {
                    correctCount++;
                }
            }
            const resultDiv = document.getElementById("result");
            resultDiv.innerHTML = `You got ${correctCount} out of 5 questions correct.`;
        });
    </script>
</body>
</html>