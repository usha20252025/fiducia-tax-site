<!DOCTYPE html>
<html>

<head>
<title>Math Speed Game</title>
</head>

<body>

<h2 id="question">Loading...</h2>

<input id="answer" type="number" autofocus>
<button onclick="submitAnswer()">Submit</button>

<p id="timer"></p>
<p id="result"></p>

<script>

let num1;
let num2;
let score = 0;
let timeLimit = 2000;
let timer;

function newQuestion(){

num1 = Math.floor(Math.random()*10);
num2 = Math.floor(Math.random()*10);

document.getElementById("question").innerText =
num1 + " + " + num2 + " = ?";

document.getElementById("answer").value = "";

timer = setTimeout(gameOver, timeLimit);

}

function submitAnswer(){

clearTimeout(timer);

let userAnswer = document.getElementById("answer").value;

if(userAnswer == (num1 + num2)){

score++;

newQuestion();

}else{

gameOver();

}

}

function gameOver(){

document.getElementById("result").innerText =
"Game Over! Score: " + score;

}

newQuestion();

</script>

</body>

</html>
