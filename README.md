<!DOCTYPE html>
<html>
<head>
  <title>Simple Gym App</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

<h1>Choose Workout Day</h1>

<div id="buttons">
  <button onclick="showWorkout('legs')">Leg Day</button>
  <button onclick="showWorkout('chest')">Chest Day</button>
  <button onclick="showWorkout('back')">Back Day</button>
  <button onclick="showWorkout('arms')">Arm Day</button>
</div>

<h2 id="title"></h2>

<ul id="exerciseList"></ul>

<script src="script.js"></script>

</body>
</html>

body{
  font-family: Arial;
  text-align:center;
  background:#111;
  color:white;
}

button{
  padding:12px;
  margin:10px;
  font-size:16px;
  border:none;
  background:#ff3c3c;
  color:white;
  border-radius:8px;
}

li{
  list-style:none;
  padding:10px;
  font-size:18px;
}

const workouts = {
  legs: ["Squats", "Lunges", "Leg Press", "Calf Raises"],
  chest: ["Bench Press", "Push Ups", "Chest Fly"],
  back: ["Pull Ups", "Deadlift", "Lat Pulldown"],
  arms: ["Bicep Curl", "Hammer Curl", "Tricep Dips"]
};

function showWorkout(day) {

  const list = document.getElementById("exerciseList");
  const title = document.getElementById("title");

  list.innerHTML = "";

  title.innerText = day.toUpperCase() + " WORKOUT";

  workouts[day].forEach(function(exercise){

    const li = document.createElement("li");
    li.innerText = exercise;

    list.appendChild(li);

  });
}
