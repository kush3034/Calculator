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
## File Structure
# Calculator Application - File Structure

## 📁 Complete File Structure

```
application/
├── calculator/                          # Main React Application Directory
│   ├── .git/                           # Git version control directory
│   ├── node_modules/                   # Dependencies (auto-generated)
│   ├── public/                         # Public assets and HTML files
│   │   ├── favicon.ico                 # Website favicon
│   │   ├── index.html                  # Main HTML template
│   │   ├── logo192.png                 # React logo (192x192)
│   │   ├── logo512.png                 # React logo (512x512)
│   │   ├── manifest.json               # Web app manifest
│   │   └── robots.txt                  # Search engine robots file
│   ├── src/                            # Source code directory
│   │   ├── App.css                     # Main app styling
│   │   ├── App.js                      # Main app component
│   │   ├── App.test.js                 # App component tests
│   │   ├── Calculator.css              # Calculator component styling
│   │   ├── Calculator.js               # Main calculator component
│   │   ├── index.css                   # Global CSS styles
│   │   ├── index.js                    # Application entry point
│   │   ├── logo.svg                    # React logo SVG
│   │   ├── reportWebVitals.js          # Performance monitoring
│   │   └── setupTests.js               # Test configuration
│   ├── .gitignore                      # Git ignore rules
│   ├── FILE_STRUCTURE.md               # This file structure documentation
│   ├── instruction.md                  # Application instructions
│   ├── package-lock.json               # Dependency lock file
│   ├── package.json                    # Project configuration
│   └── README.md                       # Project documentation
└── instruction.md                      # Root level instructions
```

## 📋 File Descriptions

### 🎯 Core Application Files

#### **Main Components**
- **`src/Calculator.js`** - Main calculator component with all functionality
- **`src/Calculator.css`** - Calculator-specific styling and layout
- **`src/App.js`** - Root React component that renders the calculator
- **`src/App.css`** - Main application styling

#### **Entry Points**
- **`src/index.js`** - Application entry point and React rendering
- **`public/index.html`** - Main HTML template

#### **Configuration Files**
- **`package.json`** - Project dependencies, scripts, and metadata
- **`package-lock.json`** - Locked dependency versions for consistency
- **`.gitignore`** - Files to exclude from Git version control

### 📚 Documentation Files

#### **Instructions & Guides**
- **`instruction.md`** - Complete application instructions and usage guide
- **`README.md`** - Project overview and setup instructions
- **`FILE_STRUCTURE.md`** - This file structure documentation

### 🎨 Assets & Public Files

#### **Icons & Images**
- **`public/favicon.ico`** - Website favicon
- **`public/logo192.png`** - React logo (192x192 pixels)
- **`public/logo512.png`** - React logo (512x512 pixels)
- **`src/logo.svg`** - React logo in SVG format

#### **Web App Files**
- **`public/manifest.json`** - Progressive Web App manifest
- **`public/robots.txt`** - Search engine crawling instructions

### 🧪 Testing & Development Files

#### **Testing**
- **`src/App.test.js`** - Unit tests for App component
- **`src/setupTests.js`** - Test configuration and setup

#### **Performance & Monitoring**
- **`src/reportWebVitals.js`** - Performance monitoring utilities

### 🎨 Styling Files

#### **CSS Files**
- **`src/index.css`** - Global CSS styles and resets
- **`src/App.css`** - Main application styling
- **`src/Calculator.css`** - Calculator-specific styling

## 🔧 Key Features by File

### Calculator Functionality (`src/Calculator.js`)
- ✅ Basic arithmetic operations (+, -, *, /)
- ✅ Clear button (C)
- ✅ Backspace button (⌫)
- ✅ Decimal point support
- ✅ Error handling
- ✅ Responsive design

### Styling (`src/Calculator.css`)
- ✅ Modern calculator design
- ✅ Grid layout for buttons
- ✅ Hover and active states
- ✅ Responsive display
- ✅ Clean, professional appearance

### Configuration (`package.json`)
- ✅ React 18.x
- ✅ Development server setup
- ✅ Build scripts
- ✅ Testing configuration

## 📦 Dependencies

### Core Dependencies
- **React** - UI library
- **React DOM** - DOM rendering
- **React Scripts** - Development tools

### Development Dependencies
- **Testing Library** - Component testing
- **Web Vitals** - Performance monitoring

## 🚀 How to Use

1. **Install Dependencies**: `npm install`
2. **Start Development Server**: `npm start`
3. **Build for Production**: `npm run build`
4. **Run Tests**: `npm test`

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

## 📁 Repository Structure

Your GitHub repository at `https://github.com/kush3034/Calculator.git` contains all these files and is ready for:
- ✅ Development
- ✅ Deployment
- ✅ Collaboration
- ✅ Version control

## Customization

You can modify the calculator by editing the `Calculator.js` and `Calculator.css` files in the `src` directory.

---

## License

This project is for educational purposes.