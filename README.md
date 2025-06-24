<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
    body {
      background: white;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator {
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      width: 300px;
    }

    .calculator input[type="text"] {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      border: 1px solid white;
      border-radius: 10px;
      padding: 10px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    .buttons button {
      padding: 20px;
      font-size: 20px;
      border: none;
      border-radius: 10px;
      background-color:skyblue;
      color: white;
      cursor: pointer;
      transition: 0.2s;
    }

    .buttons button:hover {
      background-color: skyblue;
    }

    .buttons .equal {
      grid-column: span 2;
      background-color:lightgreen;
    }

    .buttons .equal:hover {
      background-color: lightgreen;
    }

    .buttons .clear {
      background-color: red;
    }

    .buttons .clear:hover {
      background-color: red;
    }
  </style>
</head>
<body>
    <div class="calculator">
  <input type="text" id="display" readonly />
  <div class="buttons">
    <button onclick="appendValue('7')">7</button>
    <button onclick="appendValue('8')">8</button>
    <button onclick="appendValue('9')">9</button>
    <button onclick="appendValue('/')">/</button>

    <button onclick="appendValue('4')">4</button>
    <button onclick="appendValue('5')">5</button>
    <button onclick="appendValue('6')">6</button>
    <button onclick="appendValue('*')">*</button>

    <button onclick="appendValue('1')">1</button>
    <button onclick="appendValue('2')">2</button>
    <button onclick="appendValue('3')">3</button>
    <button onclick="appendValue('-')">-</button>

    <button onclick="appendValue('0')">0</button>
    <button onclick="appendValue('.')">.</button>
    <button class="equal" onclick="calculate()">=</button>
    <button onclick="appendValue('+')">+</button>

    <button class="clear" onclick="clearDisplay()">C</button>
  </div>
</div>

<script>
  function appendValue(val) {
    document.getElementById("display").value += val;
  }

  function clearDisplay() {
    document.getElementById("display").value = '';
  }

  function calculate() {
    try {
      document.getElementById("display").value = eval(document.getElementById("display").value);
    } catch {
      document.getElementById("display").value = "Error";
    }
  }
</script>
</body>
</html>
