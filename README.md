# Benfit.github.io
Calorie calculator
<!DOCTYPE html>
<html>
<head>
  <title>Calorie Calculator</title>
  <style>
    body { font-family: Arial; max-width: 400px; margin: auto; }
    input, select, button { width: 100%; margin: 5px 0; padding: 8px; }
    .brand { font-size: 12px; color: gray; margin-top: 10px; }
  </style>
</head>
<body>

<h2>Calorie Calculator</h2>

<input type="number" id="age" placeholder="Age">
<input type="number" id="weight" placeholder="Weight (kg)">
<input type="number" id="height" placeholder="Height (cm)">

<select id="gender">
  <option value="male">Male</option>
  <option value="female">Female</option>
</select>

<select id="activity">
  <option value="1.2">Sedentary</option>
  <option value="1.375">Light</option>
  <option value="1.55">Moderate</option>
  <option value="1.725">Active</option>
  <option value="1.9">Very Active</option>
</select>

<button onclick="calculate()">Calculate</button>

<h3 id="result"></h3>

<div class="brand">
  Built with AI assistance (ChatGPT)
</div>

<script>
function calculate() {
  let age = document.getElementById("age").value;
  let weight = document.getElementById("weight").value;
  let height = document.getElementById("height").value;
  let gender = document.getElementById("gender").value;
  let activity = document.getElementById("activity").value;

  let bmr;

  if (gender === "male") {
    bmr = 10 * weight + 6.25 * height - 5 * age + 5;
  } else {
    bmr = 10 * weight + 6.25 * height - 5 * age - 161;
  }

  let calories = bmr * activity;

  document.getElementById("result").innerText =
    "Daily Calories: " + Math.round(calories);
}
</script>

</body>
</html>
