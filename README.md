#CSS
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
}

.calculator {
    border: 1px solid #ccc;
    padding: 20px;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.display input {
    width: 100%;
    font-size: 2rem;
    padding: 10px;
    text-align: right;
    border: none;
    margin-bottom: 10px;
    border-radius: 5px;
    box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.1);
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

.btn {
    font-size: 1.5rem;
    padding: 20px;
    border: none;
    border-radius: 5px;
    background-color: #eee;
    cursor: pointer;
    transition: background-color 0.2s;
}

.btn:hover {
    background-color: #ddd;
}

.span-two {
    grid-column: span 2;
}

#JAVASCRIPT
function clearScreen() {
    document.getElementById("result").value = "";
}

function deleteLast() {
    let current = document.getElementById("result").value;
    document.getElementById("result").value = current.slice(0, -1);
}

function appendNumber(number) {
    document.getElementById("result").value += number;
}

function appendOperator(operator) {
    let current = document.getElementById("result").value;
    if (current && "+-*/".includes(current.slice(-1))) {
        document.getElementById("result").value = current.slice(0, -1) + operator;
    } else if (current) {
        document.getElementById("result").value += operator;
    }
}

function calculate() {
    let current = document.getElementById("result").value;
    if (current) {
        try {
            document.getElementById("result").value = eval(current);
        } catch (e) {
            alert("Invalid expression");
        }
    }
}

#HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <link rel="stylesheet" href="CNstyle3.css">
</head>
<body>
        <div class="calculator">
        <div class="display">
            <input type="text" id="result" readonly>
        </div>
        <div class="buttons">
            <button class="btn" onclick="clearScreen()">C</button>
            <button class="btn" onclick="deleteLast()">DEL</button>
            <button class="btn" onclick="appendOperator('/')">/</button>
            <button class="btn" onclick="appendOperator('*')">*</button>
            <button class="btn" onclick="appendNumber('7')">7</button>
            <button class="btn" onclick="appendNumber('8')">8</button>
            <button class="btn" onclick="appendNumber('9')">9</button>
            <button class="btn" onclick="appendOperator('-')">-</button>
            <button class="btn" onclick="appendNumber('4')">4</button>
            <button class="btn" onclick="appendNumber('5')">5</button>
            <button class="btn" onclick="appendNumber('6')">6</button>
            <button class="btn" onclick="appendOperator('+')">+</button>
            <button class="btn" onclick="appendNumber('1')">1</button>
            <button class="btn" onclick="appendNumber('2')">2</button>
            <button class="btn" onclick="appendNumber('3')">3</button>
            <button class="btn span-two" onclick="appendNumber('0')">0</button>
            <button class="btn" onclick="appendNumber('.')">.</button>
            <button class="btn span-two" onclick="calculate()">=</button>
        </div>
    </div>

    <script src="CNscript3.js"></script>
</body>
</html>
