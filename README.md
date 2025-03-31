# web_programming
Extension of web development login page in addition with javascript
#loginpage 

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Login Page</title>
<style>
body {
font-family: Arial, Helvetica, sans-serif;
background-image: url('C:/Users/Mohit/Downloads/signup.jpg');
background-position:center;
background-repeat:no-repeat;
background-size:cover;
margin: 0;
padding: 0;
min-height: 100vh;
}
.container {
width: 300px;
margin: 0 auto;
margin-top: 100px;
background-color: white;
padding: 20px;
box-shadow: 0 0 10px rgba(186, 9, 9, 0.2);
border-radius: 5px;
}
.container h2 {
text-align: center;
}
.form-group {
margin-bottom: 15px;
}
.form-group label {
display: block;
margin-bottom: 5px;
}
.form-group input {
width: 90%;
padding: 10px;
border: 1px solid #ccc;
border-radius: 3px;
}
.form-group button {
width: 100%;
padding: 10px;
background-color: #007BFF;
color: #fff;
border: none;
border-radius: 3px;
cursor: pointer;
}
.form-group button:hover {
background-color: #0056b3;
}
</style>
</head>
<body  >
<div class="container">
<h2>Login</h2>
<form id="loginForm" onsubmit="return login()">
<div class="form-group">
<label for="username">Username</label>
<input type="text" id="username" placeholder="Enter username"required>
</div><br>
<div class="form-group">
<label for="password">Password</label>
<input type="password" id="password" placeholder="Enter password"required>
</div><br>
<div class="form-group">
<button type="submit" onclick="login()">Login</button>
</div><br>
<div class="link">
    <a href="#" onclick="forgotPassword()">Forgot Password?</a>
    <br>
<div class="link">
Don't have an account?<a
href="file:///C:/Users/Mohit/OneDrive/Desktop/signup.html"> Sign up</a>
</div>
</form>
</div>
<script>
    function validateForm() {
        var username = document.getElementById("username").value;
        var password = document.getElementById("password").value;


        if(username ==="" || password ===""){
            alert("Username and password must be filled out");
            return false;
        }
        return true;
    }
    function login() {
    
    event.preventDefault(); 


    if (validateForm()) {
        
        window.location.href = "file:///C:/Users/Mohit/OneDrive/Desktop/final.html";
    }
   
}


    
    function forgotPassword() {
        var username = prompt("Please enter your mobile number or email address:");
        if (username !== null && username !== "") {
            alert("A password reset link has been sent to your email address.");
        }
    }
    document.getElementById("loginForm").addEventListener("keydown", function(event) {
        if (event.key === "Enter") {
            event.preventDefault();
        }
    });
</script>
</body>
</html>


#signinpage

<!DOCTYPE html>
 <html lang="en">
 <head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Sign up page</title>
 
 <style>
 body {
 font-family: Arial, Helvetica, sans-serif;
 background-position:centre;
 background-repeat:no-repeat;
 background-size:cover;
 margin: 0;
 padding: 0;
 }
 .container1 {
 width: 350px;
 margin: 645px;
 margin-top: 100px;
 background-color:white;
 padding: 30px;
 box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
 border-radius: 5px;
 height:600px;
 display:block;
 }
 .container1 h2 {
 text-align: center;
}
 .form-group1 {
 margin-bottom: 15px;
 }
 .form-group1 label {
    display: block;
    margin-bottom: 5px;
    }
    .form-group1 input {
    width: 90%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
    }
    .form-group1 button {
    width: 100%;
    padding: 10px;
    background-color: #007BFF;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    }
    .form-group1 button:hover {
    background-color: #0056b3;
    }
    #password-strength {
    display: block; 
    margin-top: 20px; 
    color: red; 
}


    small{
        color:red
        }
        </style>
        </head>
        <body background="C:\Users\Mohit\Downloads\signup.jpg">
           <div class="container1">
               <h2>Sign up</h2><br>
              <form class="content" action="file:///C:/Users/Mohit/OneDrive/Desktop/final.html" onsubmit="return validateForm()" onsubmit="return validateEmail()">
               <div class="form-group1">
               <label for="username">Username</label>
               <input type="text" id="username" placeholder="Create username">
               </div>
               <div class="form-group1">
               <label for="email">Email</label>
               <input type="email" id="email" placeholder="Enter Email">
               </div><br>
               <div class="form-group1">
               <label for="password"> Create Password</label>
               <div style="position:relative;">
               <input type="password" id="password" placeholder="Create Password"  onkeyup="checkPasswordStrength()">
               <input type="checkbox" onclick="togglePasswordVisibility()" style="position:absolute; right:170px; top: 120%; transform: translateY(-50%);">
               <label for="togglePassword" style="position:absolute; right:200px; top: 130%; transform: translateY(-50%); cursor: pointer;">Show Password</label>
               </div>
               <small id="password-strength"></small>
               </div><br>
               <div class="form-group1">
               <label for="Confirmpassword">Confirm Password</label>
               <input type="password" id="Confirmpassword"placeholder="Confirm Password">
               </div><br>
               <div class="form-group1">
               <button type="submit">Sign up</button>
              </div>
               </form>
               </div>
               <script>
                   function validateForm() {
                       var username = document.getElementById("username").value;
                       var email = document.getElementById("email").value;
                       var password = document.getElementById("password").value;
                       var confirmPassword = document.getElementById("Confirmpassword").value;
               
                       if (username === "" || email === "" || password === "" || confirmPassword === "") {
                           alert("All fields must be filled out");
                           return false;
                       }
                       if (password !== confirmPassword) {
                        alert("Passwords do not match");
                        return false;
                    }
            
                    return true;
                }
                function checkPasswordStrength() {
    var password = document.getElementById("password").value;
    var strengthText = document.getElementById("password-strength");
    
    // Reset strength message
    strengthText.textContent = "";


    if (password.length < 8) {
        // Password too short
        strengthText.textContent = "Password must be 8 or more characters long.";
        strengthText.style.color = "red";
    } else {
        // Initialize strength criteria
        var hasUpperCase = /[A-Z]/.test(password);
        var hasLowerCase = /[a-z]/.test(password);
        var hasNumbers = /\d/.test(password);
        var hasSpecialChars = /[^A-Za-z0-9]/.test(password);
        var strength = 0;


        // Check for each criteria
        if (hasUpperCase) strength++;
        if (hasLowerCase) strength++;
        if (hasNumbers) strength++;
        if (hasSpecialChars) strength++;


        // Display strength level based on criteria met
        if (strength < 4) {
            strengthText.textContent = "Password must include uppercase and lowercase letters, numbers, and special characters.";
            strengthText.style.color = "orange";
        } else {
            strengthText.textContent = "Strong password✅";
            strengthText.style.color = "green";
        }
    }
}


                
            function togglePasswordVisibility() {
                var passwordInput = document.getElementById("password");
                if (passwordInput.type === "password") {
                    passwordInput.type = "text";
                } else {
                    passwordInput.type = "password";
                }
            }
            function validateEmail() {
                var email = document.getElementById("email").value;
                var emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            
                if (!emailRegex.test(email)) {
                    alert("Please enter a valid email address");
                    return false;
                }
            
                return true;
            } 
            
            </script>
            </body>
            </html>


#lastpage

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Simple Website</title>
<style>
body {
font-family: Arial, sans-serif;
}
header {
background-color: rgb(164, 121, 147);
color: rgb(35, 28, 28);
text-align: center;
padding: 10px;
}
nav {
text-align: center;
}
nav a {
text-decoration: none;
margin: 10px;
color: black;
}
section {
margin: 20px;
}
footer {
background-color: black;
color: whitesmoke;
text-align: center;
padding: 10px;
}
</style>
</head>
<body>
<header>
<h1>OUR VALIDATED JS PROJECT</h1>
</header>
<nav>
<a
href="https://www.ruiacollege.edu/Department/Deptindex.aspx?page=a&ItemID=ca
eae&nDeptID=caaig">Home</a>
<a
href="https://www.ruiacollege.edu/Department/DisplayDeptPage.aspx?page=eci&Ite
mID=ego&nDeptID=caaig">About</a>
<a
href="https://www.ruiacollege.edu/Department/DisplayDeptPage.aspx?page=ecg&It
emID=egi&nDeptID=caaig">Contact</a>
</nav>
<section>
<h2>About Us</h2>
<p>The Group Members Of This Project are <br>Soyebah Majeed<br>
Harsh Nigam<br>
Aryan Mishra<br>
Suraj Salve<br>
Soham Mane<br>
Mahalaxmi Nadar<br>
Grishma Maithania<br></p>
</section>
<section>
<h2>Contact Us</h2>
<p>You can reach us by calling or by whatsapp on this number
"9323230105"</p>
</section>
<footer>
&copy; GROUP 4 PROJECT ON TOP
</footer>
</body>
</html>
