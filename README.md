<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8" />
    <title>Basic Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Basic Calculator</h1>
   <div class="calculator">
    
    <input type="text" id="display" disabled>
    <div class="buttons">
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendToDisplay('/')">/</button>
            <button onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="calculateResult()" id="equals">=</button>
    </div>
   </div>
   <script src="calculator.js"></script> 
</body>
</html>




body{
    display:flex;
    justify-content:center;
    align-items:center;
 
    height:100vh;
    margin:0;
    background-color:aqua;
    flex-direction:column;

}
.container{
    text-align:center;
}
h1 {
    
 
    
        margin-bottom: 30px; /* Adjust this value to change the space */
        font-size: 2em;
        color: #333;


  
 }
.calculator{
    border:1px solid #ccc;
    border-radius:8px;
    box-shadow:0 0 10px rgba(0,0,0,0.1);
    width:200px;
}
#display{
    width:90%;
    height:50px;
    text-align:right;
    padding:10px;
    border:none;
    font-size:1.5em;
    background-color: antiquewhite;
    border-radius:8px 8px 0 0 ;

}
.buttons{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:1px;
}
button{
    width:100%;
    height:50px;
    font-size:1.2em;
    border:none;
    background-color: antiquewhite;
    cursor:pointer;
}
button:hover{
    background-color: chocolate;

}
button:active{
    background-color:cornflowerblue;
}
#equals{
    grid-column:span 4;
    background-color: darkkhaki;
    color:white;
}

function appendToDisplay(value) {
    document.getElementById('display').value += value;
}

function clearDisplay() {
    document.getElementById('display').value = '';
}

function calculateResult() {
    const display = document.getElementById('display');
    try {
       
        display.value = eval(display.value);
    } catch (error) {
      
        display.value = 'Error';
    }
}
