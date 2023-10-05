# login1-cv-page
<!DOCTYPE html>
<html>
<head>
    <title>Login Page</title>
</head>
<body>
    <div id="loginPage">
        <h2>Login Page</h2>
        <form id="loginForm">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required><br><br>
            
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required><br><br>
            
            <input type="button" value="Login" onclick="checkLogin()">
        </form>

        <p id="loginMessage"></p>
    </div>

    <div id="cvPage" style="display:none;">
        <h2>Jacob P James CV View</h2>
        <!-- Your CV content goes here -->
        <p>This is your CV content. You can display your CV information here.</p>
        
        <input type="button" value="Logout" onclick="logout()">
    </div>

    <script>
        function checkLogin() {
            var username = document.getElementById("username").value;
            var password = document.getElementById("password").value;
            var loginPage = document.getElementById("loginPage");
            var cvPage = document.getElementById("cvPage");

            if (username === "jac" && password === "xxx") {
                // Hide the login page and show the CV page
                loginPage.style.display = "none";
                cvPage.style.display = "block";
            } else {
                document.getElementById("loginMessage").innerHTML = "Login failed. Please check your username and password.";
            }
        }

        function logout() {
            var loginPage = document.getElementById("loginPage");
            var cvPage = document.getElementById("cvPage");
            
            // Hide the CV page and show the login page
            cvPage.style.display = "none";
            loginPage.style.display = "block";
            
            // Clear the username and password fields
            document.getElementById("username").value = "";
            document.getElementById("password").value = "";
            
            // Clear the login message
            document.getElementById("loginMessage").innerHTML = "Logged out successfully.";
        }
    </script>
</body>
</html>
