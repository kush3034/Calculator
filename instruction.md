# Calculator Application - Instructions

## Overview

This is a simple calculator application built with React.js. It supports basic arithmetic operations: addition, subtraction, multiplication, and division.

---

## How to Run the Application

1. **Install Dependencies**

   Open a terminal in the project directory and run:
   ```sh
   npm install
   ```

2. **Start the Application**

   Start the development server with:
   ```sh
   npm start
   ```

   The app will open in your default browser at [http://localhost:3000](http://localhost:3000).

---

## Features

- Addition, subtraction, multiplication, and division
- Clear (`C`) button to reset input and result
- Backspace (`⌫`) button to remove the last character
- Responsive and user-friendly interface

---

## How to Use

- Click the number and operator buttons to enter your calculation.
- Press `=` to see the result.
- Use `C` to clear everything.
- Use `⌫` to delete the last character.

---
## Code of functionality to use in calculator
1. **Calculator.js**
    ``` import React, { useState } from 'react';
        import './Calculator.css';

        function Calculator() {
            const [input, setInput] = useState('');
            const [result, setResult] = useState('');

            const handleClick = (value) => {
                setInput((prev) => prev + value);
            };

            const handleClear = () => {
                setInput('');
                setResult('');
            };

            const handleEqual = () => {
                try {
                    // eslint-disable-next-line no-eval
                    const evalResult = eval(input);
                    setResult(evalResult);
                } catch {
                    setResult('Error');
                }
            };

            const handleBackspace = () => {
                setInput((prev) => prev.slice(0, -1));
            };
  
            return (
            <div className="calculator-container">
                <div className="display">
                    <div className="input">{input}</div>
                    <div className="result">{result}</div>
                </div>
                <div className="buttons">
                    <button onClick={handleClear}>C</button>
                    <button onClick={handleBackspace}>⌫</button>
                    <button onClick={() => handleClick('/')}>/</button>
                    <button onClick={() => handleClick('*')}>*</button>
                    <button onClick={() => handleClick('-')}>-</button>
                    <button onClick={() => handleClick('7')}>7</button>
                    <button onClick={() => handleClick('8')}>8</button>
                    <button onClick={() => handleClick('9')}>9</button>
                    <button onClick={() => handleClick('+')}>+</button>
                    <button onClick={() => handleClick('4')}>4</button>
                    <button onClick={() => handleClick('5')}>5</button>
                    <button onClick={() => handleClick('6')}>6</button>
                    <button onClick={handleEqual}>=</button>
                    <button onClick={() => handleClick('1')}>1</button>
                    <button onClick={() => handleClick('2')}>2</button>
                    <button onClick={() => handleClick('3')}>3</button>
                    <button onClick={() => handleClick('0')}>0</button>
                    <button onClick={() => handleClick('.')}>.</button>
                </div>
            </div>
        );
    }
    ```

2. **Calculator.css**
``` .calculator-container {
        width: 260px;
        margin: 40px auto;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        background: #f9f9f9;
    }
    .display {
        background: #222;
        color: #fff;
        border-radius: 5px;
        padding: 10px;
        margin-bottom: 15px;
        min-height: 50px;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .input {
        font-size: 1.2em;
        min-height: 24px;
    }
    .result {
        font-size: 1.5em;
        text-align: right;
        min-height: 26px;
    }
    .buttons {
    display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 10px;
    }
    button {
        padding: 15px;
        font-size: 1.1em;
        border: none;
        border-radius: 5px;
        background: #e0e0e0;
        cursor: pointer;
        transition: background 0.2s;
    }
    button:hover {
        background: #bdbdbd;
    }
    button:active {
        background: #9e9e9e;
    }
```

export default Calculator;
## How to Save to GitHub

1. **Initialize Git (if not already done):**
   ```sh
   git init
   ```

2. **Add all files:**
   ```sh
   git add .
   ```

3. **Commit your changes:**
   ```sh
   git commit -m "Initial commit"
   ```

4. **Add your GitHub repository as remote:**
   ```sh
   git remote add origin https://github.com/your-username/your-repo.git
   ```

5. **Push to GitHub:**
   ```sh
   git branch -M main
   git push -u origin main
   ```

---

## Customization

You can modify the calculator by editing the `Calculator.js` and `Calculator.css` files in the `src` directory.

---

## License

This project is for educational purposes.