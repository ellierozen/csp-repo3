---
toc: true
comments: false
layout: post
title: Tic Tac Toe
description: Tic tac toe game
type: tangibles
courses: { compsci: {week: 2} }
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tic-Tac-Toe</title>
    <style>
        table {
            border-collapse: collapse;
        }
        td {
            width: 50px;
            height: 50px;
            text-align: center;
            font-size: 24px;
            border: 1px solid #000;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Tic-Tac-Toe</h1>
    <table id="ticTacToe">
        <tr>
            <td onclick="makeMove(0, 0)"></td>
            <td onclick="makeMove(0, 1)"></td>
            <td onclick="makeMove(0, 2)"></td>
        </tr>
        <tr>
            <td onclick="makeMove(1, 0)"></td>
            <td onclick="makeMove(1, 1)"></td>
            <td onclick="makeMove(1, 2)"></td>
        </tr>
        <tr>
            <td onclick="makeMove(2, 0)"></td>
            <td onclick="makeMove(2, 1)"></td>
            <td onclick="makeMove(2, 2)"></td>
        </tr>
    </table>
    <p id="message"></p>
    
    <script>
        let currentPlayer = 'X';
        let gameBoard = [
            ['', '', ''],
            ['', '', ''],
            ['', '', '']
        ];
        let gameOver = false;

        function makeMove(row, col) {
            if (gameOver || gameBoard[row][col] !== '') return;

            gameBoard[row][col] = currentPlayer;
            document.getElementById('ticTacToe').rows[row].cells[col].textContent = currentPlayer;

            if (checkWin(row, col)) {
                document.getElementById('message').textContent = `Player ${currentPlayer} wins!`;
                gameOver = true;
            } else if (isBoardFull()) {
                document.getElementById('message').textContent = "It's a draw!";
                gameOver = true;
            } else {
                currentPlayer = (currentPlayer === 'X') ? 'O' : 'X';
            }
        }

        function checkWin(row, col) {
            const symbols = ['X', 'O'];

            for (const symbol of symbols) {
                if (
                    (gameBoard[row][0] === symbol && gameBoard[row][1] === symbol && gameBoard[row][2] === symbol) ||
                    (gameBoard[0][col] === symbol && gameBoard[1][col] === symbol && gameBoard[2][col] === symbol) ||
                    (gameBoard[0][0] === symbol && gameBoard[1][1] === symbol && gameBoard[2][2] === symbol) ||
                    (gameBoard[0][2] === symbol && gameBoard[1][1] === symbol && gameBoard[2][0] === symbol)
                ) {
                    return true;
                }
            }

            return false;
        }

        function isBoardFull() {
            for (const row of gameBoard) {
                if (row.includes('')) {
                    return false;
                }
            }
            return true;
        }
    </script>
</body>
</html>
