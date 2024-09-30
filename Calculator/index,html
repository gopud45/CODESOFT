let currentInput = '';
let operation = '';
let previousInput = '';

function updateDisplay() {
    document.getElementById('display').textContent = currentInput || '0';
}

function appendNumber(number) {
    if (currentInput === '0' && number !== '.') {
        currentInput = number;
    } else {
        currentInput += number;
    }
    updateDisplay();
}

function appendDecimal() {
    if (!currentInput.includes('.')) {
        currentInput += '.';
        updateDisplay();
    }
}

function setOperation(op) {
    if (currentInput === '' && op !== '-') return;
    
    if (previousInput !== '') {
        calculate();
    }
    
    operation = op;
    previousInput = currentInput;
    currentInput = '';
}

function clearDisplay() {
    currentInput = '';
    previousInput = '';
    operation = '';
    updateDisplay();
}

function calculate() {
    if (previousInput === '' || currentInput === '') return;

    const prev = parseFloat(previousInput);
    const current = parseFloat(currentInput);

    switch (operation) {
        case '+':
            currentInput = (prev + current).toString();
            break;
        case '-':
            currentInput = (prev - current).toString();
            break;
        case '*':
            currentInput = (prev * current).toString();
            break;
        case '/':
            if (current !== 0) {
                currentInput = (prev / current).toString();
            } else {
                currentInput = 'Error'; // Handle division by zero
            }
            break;
    }

    operation = '';
    previousInput = '';
    updateDisplay();
}
