# Coursevita-Team6
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ticketing System for Learner Support</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-image: url('image1.jpg'); 
            background-size: cover;
            background-attachment: fixed;
            transition: background-image 0.5s ease;
        }
        .login-bg {
            background-image: url('image2.jpg'); 
        }
        .top-right {
            position: absolute;
            top: 20px;
            right: 20px;
        }
        .login-btn {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border-radius: 5px;
            text-decoration: none;
            cursor: pointer;
            border: none;
        }
        .login-btn:hover {
            background-color: #0056b3;
        }
        .container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #fff;
            background-color: rgba(0, 0, 0, 0.6); 
            text-align: center;
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
        }
        .login-box {
            background-color: #1a1a1a;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            display: none;
        }
        input[type="text"], input[type="password"], textarea, select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: none;
            border-radius: 5px;
        }
        .btn {
            width: 100%;
            padding: 10px;
            background-color: #28a745;
            border: none;
            border-radius: 5px;
            color: white;
            font-size: 16px;
            cursor: pointer;
        }
        .btn:hover {
            background-color: #218838;
        }
        .ticket-box {
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            margin-top: 20px;
        }
        .ticket-btn {
            background-color: #007bff;
            padding: 10px 20px;
            color: white;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none;
        }
        .ticket-btn:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="top-right">
        <button class="login-btn" onclick="showLogin()">Login/Register</button>
    </div>

    <div class="container" id="main-container">
        <h1>Welcome to the Learner Support Ticketing System</h1>

        <!-- Login Box -->
        <div class="login-box" id="login-box">
            <h2>Login</h2>
            <input type="text" id="username" placeholder="Username">
            <input type="password" id="password" placeholder="Password">
            <button class="btn" onclick="login()">Login</button>
        </div>
        <div class="ticket-box" id="ticket-box">
            <h2>Submit a Support Ticket</h2>
            <select id="category">
                <option value="Technical Issue">Technical Issue</option>
                <option value="Course Material Issue">Course Material Issue</option>
                <option value="Other">Other</option>
            </select>
            <textarea id="description" placeholder="Describe your issue"></textarea>
            <select id="priority">
                <option value="Low">Low</option>
                <option value="Medium">Medium</option>
                <option value="High">High</option>
            </select>
            <button class="btn" onclick="submitTicket()">Submit Ticket</button>
        </div>
    </div>
    <script>
        function showLogin() {
            document.getElementById("login-box").style.display = "block";
            document.body.classList.add("login-bg");
        }
        function login() {
            var username = document.getElementById("username").value;
            var password = document.getElementById("password").value;
            if (username === "Coursevita" && password === "Team6") {
                document.getElementById("login-box").style.display = "none";
                document.getElementById("ticket-box").style.display = "flex";
                document.body.classList.remove("login-bg");
            } else {
                alert("Invalid login credentials!");
            }
        }
        function submitTicket() {
            var category = document.getElementById("category").value;
            var description = document.getElementById("description").value;
            var priority = document.getElementById("priority").value;
            if (description === "") {
                alert("Please provide a description of the issue.");
                return;
            }
            alert("Ticket Submitted!\nCategory: " + category + "\nPriority: " + priority + "\nDescription: " + description);
            document.getElementById("ticket-box").style.display = "none";
            document.getElementById("main-container").innerHTML = "<h2>Thank you, your ticket has been submitted!</h2>";
        }
    </script>
</body>
</html>
