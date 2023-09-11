---
toc: true
comments: false
layout: post
title: Guess Number Game
description: guess a number 1-100
type: tangibles
courses: { compsci: {week: 3} }
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guess the Number</title>
</head>
<body>
    <h1>Guess the Number Game</h1>
    <p>Guess a number between 1 and 100:</p>
    <input type="number" id="guess" min="1" max="100">
    <button onclick="checkGuess()">Submit Guess</button>
    <p id="message"></p>

    <script>
        // Generate a random number between 1 and 100
        const randomNumber = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        function checkGuess() {
            const guess = parseInt(document.getElementById('guess').value);

            if (isNaN(guess) || guess < 1 || guess > 100) {
                document.getElementById('message').textContent = 'Please enter a valid number between 1 and 100.';
                return;
            }

            attempts++;

            if (guess === randomNumber) {
                document.getElementById('message').textContent = `Congratulations! You guessed the number ${randomNumber} in ${attempts} attempts.`;
                document.getElementById('guess').disabled = true;
            } else if (guess < randomNumber) {
                document.getElementById('message').textContent = 'Try a higher number.';
            } else {
                document.getElementById('message').textContent = 'Try a lower number.';
            }
        }
    </script>
</body>
</html>
