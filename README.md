# Calculator

## Index.html

```
<html>
<head>
    <title>Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        h1{
            text-align: center;
            font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        }

        #calculator-container {
            background-color:cornflowerblue;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin: 5px;
            color:black; 
            border-radius: 10px;
        }

        table {
            margin-top: 20px;
        }

        button {
            padding: 30px;
            font-size: 20px;
        }

        /* Define colors for operators */
        button[data-operator="+"] {
            background-color:darksalmon;
        }

        button[data-operator="-"] {
            background-color:darksalmon;
        }

        button[data-operator="*"] {
            background-color: darksalmon;
        }

        button[data-operator="/"] {
            background-color:darksalmon;
        }

        button[data-operator="%"] {
            background-color:darksalmon;
        }

        button[data-operator="sqrt"] {
            background-color:darksalmon;
        }
    </style>
</head>
<body>
    <div id="calculator-container">
        <h1>CALCULATOR</h1>
        <input type="text" id="display" readonly>
        <table>
            <tr>
                <td><button onclick="appendToDisplay('1')">1</button></td>
                <td><button onclick="appendToDisplay('2')">2</button></td>
                <td><button onclick="appendToDisplay('3')">3</button></td>
                <td><button data-operator="+" onclick="appendToDisplay('+')" style="color: black;">+</button></td>
            </tr>
            <tr>
                <td><button onclick="appendToDisplay('4')">4</button></td>
                <td><button onclick="appendToDisplay('5')">5</button></td>
                <td><button onclick="appendToDisplay('6')">6</button></td>
                <td><button data-operator="-" onclick="appendToDisplay('-')" style="color:black;">-</button></td>
            </tr>
            <tr>
                <td><button onclick="appendToDisplay('7')">7</button></td>
                <td><button onclick="appendToDisplay('8')">8</button></td>
                <td><button onclick="appendToDisplay('9')">9</button></td>
                <td><button data-operator="*" onclick="appendToDisplay('*')" style="color:black;">*</button></td>
            </tr>
            <tr>
                <td><button onclick="appendToDisplay('0')">0</button></td>
                <td><button data-operator="%" onclick="appendToDisplay('%')">%</button></td>
                <td><button data-operator="sqrt" onclick="calculateSquareRoot()">&#8730;</button></td>
                <td><button data-operator="/" onclick="appendToDisplay('/')" style="color:black;">/</button></td>
            </tr>
            <tr>
                <td><button onclick="clearDisplay()">C</button></td>
                <td><button onclick="appendToDisplay('.')">.</button></td>
                <td><button onclick="appendToDisplay('00')">00</button></td>
                <td><button onclick="calculateResult()">=</button></td>
            </tr>
        </table>
    </div>
    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculateResult() {
            try {
                document.getElementById('display').value = eval(document.getElementById('display').value);
            } catch (error) {
                document.getElementById('display').value = 'Error';
            }
        }

        function calculateSquareRoot() {
            const inputValue = document.getElementById('display').value;
            const result = Math.sqrt(parseFloat(inputValue));
            document.getElementById('display').value = result;
        }
    </script>
</body>
</html>
```

## output

![image](https://github.com/AshikaJubi/calculator/assets/129098066/6249186e-0317-4552-a0c5-bac5f9418e56)
