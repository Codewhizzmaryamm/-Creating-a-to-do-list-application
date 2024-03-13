Front End (HTML, CSS, JavaScript):
HTML (index.html):

html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <title>To-Do List App</title>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button onclick="addTask()">Add Task</button>
        <ul id="taskList"></ul>
    </div>
    <script src="app.js"></script>
</body>
</html>
CSS (styles.css):

css

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    text-align: center;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    background-color: #fff;
    margin: 10px;
    padding: 10px;
    border-radius: 5px;
    display: flex;
    justify-content: space-between;
}
JavaScript (app.js):

javascript

function addTask() {
    const taskInput = document.getElementById('taskInput');
    const taskList = document.getElementById('taskList');

    if (taskInput.value.trim() !== '') {
        const li = document.createElement('li');
        li.innerHTML = `
            <span>${taskInput.value}</span>
            <button onclick="removeTask(this)">Delete</button>
        `;
        taskList.appendChild(li);
        taskInput.value = '';
    }
}

function removeTask(button) {
    const li = button.parentElement;
    li.remove();
}

Back End (Node.js):
Install Node.js and npm:
Install Node.js from https://nodejs.org/, which includes npm (Node Package Manager).

Initialize Your Project:
Open a terminal in your project folder and run:

bash

npm init -y
Install Express:

bash
Copy code
npm install express
Create Server (server.js):

javascript

const express = require('express');
const app = express();
const port = 3000;

app.use(express.static('public'));

app.listen(port, () => {
    console.log(`Server is running at http://localhost:${port}`);
});
Run Your Application:
In the terminal, run:

bash

node server.js
Visit http://localhost:3000 to see your to-do list app in action.

This is a basic example, and you can enhance and customize it based on your requirements.
