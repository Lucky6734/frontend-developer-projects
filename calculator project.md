# frontend-developer-projects
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        .calculator {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        .display {
            width: 100%;
            height: 50px;
            font-size: 1.5em;
            text-align: right;
            margin-bottom: 10px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            font-size: 1.2em;
            padding: 10px;
            border: none;
            background: #ddd;
            cursor: pointer;
        }
        button.operator {
            background: orange;
            color: white;
        }
        button.equal {
            background: green;
            color: white;
        }
        button.clear {
            background: red;
            color: white;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" class="display" disabled>
        <div class="buttons">
            <button class="clear" onclick="clearDisplay()">C</button>
            <button onclick="appendValue('/')">/</button>
            <button onclick="appendValue('*')">*</button>
            <button onclick="appendValue('-')">-</button>
            
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button class="operator" onclick="appendValue('+')">+</button>
            
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button class="operator" onclick="appendValue('.')">.</button>
            
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button class="equal" onclick="calculateResult()">=</button>
            
            <button onclick="appendValue('0')">0</button>
        </div>
    </div>
    <script>
        function appendValue(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculateResult() {
            try {
                let result = eval(document.getElementById('display').value);
                if (!isFinite(result)) {
                    throw new Error('Math Error');
                }
                document.getElementById('display').value = result;
            } catch (error) {
                alert('Invalid Input!');
                clearDisplay();
            }
        }
    </script>
</body>
</html>
                                                                                                        