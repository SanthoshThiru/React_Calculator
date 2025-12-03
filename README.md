# Ex04 Simple Calculator - React Project
## Date:13.10.2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
# Exp.jsx
```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [display, setDisplay] = useState("0");

  const handleClick = (value) => {
    if (display === "0" || display === "Error") {
      setDisplay(value);
    } else {
      setDisplay(display + value);
    }
  };

  const handleClear = () => setDisplay("0");

  const handleBackspace = () => {
    if (display.length > 1) setDisplay(display.slice(0, -1));
    else setDisplay("0");
  };

  const calculate = () => {
    try {
      const expression = display.replace(/×/g, "*").replace(/÷/g, "/");
      // Use eval safely with validation
      if (/[^0-9+\-*/.%()]/.test(expression)) throw new Error("Invalid");
      const result = eval(expression);
      setDisplay(result.toString());
    } catch {
      setDisplay("Error");
    }
  };

  return (
    <div className="app-container">
      <div className="calculator">
        <div className="display">{display}</div>
        <div className="buttons">
          <button onClick={handleClear} className="button special">AC</button>
          <button onClick={handleBackspace} className="button special">⌫</button>
          <button onClick={() => handleClick("%")} className="button special">%</button>
          <button onClick={() => handleClick("÷")} className="button operator">÷</button>

          <button onClick={() => handleClick("7")} className="button">7</button>
          <button onClick={() => handleClick("8")} className="button">8</button>
          <button onClick={() => handleClick("9")} className="button">9</button>
          <button onClick={() => handleClick("×")} className="button operator">×</button>

          <button onClick={() => handleClick("4")} className="button">4</button>
          <button onClick={() => handleClick("5")} className="button">5</button>
          <button onClick={() => handleClick("6")} className="button">6</button>
          <button onClick={() => handleClick("-")} className="button operator">−</button>

          <button onClick={() => handleClick("1")} className="button">1</button>
          <button onClick={() => handleClick("2")} className="button">2</button>
          <button onClick={() => handleClick("3")} className="button">3</button>
          <button onClick={() => handleClick("+")} className="button operator">+</button>

          <button onClick={() => handleClick("0")} className="button zero">0</button>
          <button onClick={() => handleClick(".")} className="button">.</button>
          <button onClick={calculate} className="button equal">=</button>
        </div>
      </div>
    </div>
  );
}

export default App;


```
# App.css
```css
/* Container */
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #4facfe, #00f2fe);
  font-family: "Poppins", sans-serif;
}

/* Calculator body */
.calculator {
  width: 340px;
  border-radius: 16px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.25);
  background-color: #1e1e1e;
  overflow: hidden;
  transition: transform 0.2s;
}

.calculator:hover {
  transform: translateY(-4px);
}

/* Display area */
.display {
  background-color: #111;
  color: #00ffcc;
  font-size: 2.5rem;
  padding: 25px 20px;
  text-align: right;
  word-wrap: break-word;
  border-bottom: 1px solid #333;
  min-height: 3.5rem;
}

/* Button grid */
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

/* Buttons */
.button {
  padding: 20px;
  font-size: 1.4rem;
  border: 1px solid #333;
  cursor: pointer;
  background-color: #2a2a2a;
  color: white;
  transition: background 0.2s, transform 0.1s;
}

.button:hover {
  background-color: #3a3a3a;
}

.button:active {
  transform: scale(0.96);
}

/* Operator buttons */
.operator {
  background-color: #ff9500;
  color: #fff;
}

.operator:hover {
  background-color: #e58b00;
}

/* Special buttons */
.special {
  background-color: #505050;
}

.special:hover {
  background-color: #6a6a6a;
}

/* Equals button */
.equal {
  background-color: #00c853;
  color: #fff;
}

.equal:hover {
  background-color: #00a844;
}

/* Zero spans 2 columns */
.zero {
  grid-column: span 2;
}

```



## OUTPUT
<img width="1919" height="1073" alt="image" src="https://github.com/user-attachments/assets/ee56be5b-ccd3-44f6-b2d2-70ca725ca90a" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
