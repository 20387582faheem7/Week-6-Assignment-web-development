# Week-6-Assignment-web-development
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Events & Interactivity</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }

        button {
            margin: 5px;
            padding: 10px;
            cursor: pointer;
        }

        #hover-box {
            width: 200px;
            height: 100px;
            background-color: lightgray;
            margin: 10px auto;
            line-height: 100px;
            font-weight: bold;
        }

        .error-message {
            color: red;
            font-size: 12px;
        }
    </style>
</head>
<body>

    <h1>JavaScript Events & Interactivity</h1>

    <!-- Click Event -->
    <button id="click-btn">Click Me</button>
    <p id="click-message"></p>

    <!-- Mouseover Event -->
    <div id="hover-box">Hover Over Me</div>
    <p id="hover-message"></p>

    <!-- Form with Validation -->
    <form id="user-form">
        <label for="name">Name:</label>
        <input type="text" id="name" required>
        <small id="name-error" class="error-message"></small>
        <br><br>

        <label for="email">Email:</label>
        <input type="email" id="email" required>
        <small id="email-error" class="error-message"></small>
        <br><br>

        <button type="submit">Submit</button>
    </form>

    <script>
        // Click Event
        document.getElementById("click-btn").addEventListener("click", function() {
            document.getElementById("click-message").innerText = "Button Clicked!";
        });

        // Mouseover Event
        document.getElementById("hover-box").addEventListener("mouseover", function() {
            document.getElementById("hover-message").innerText = "Mouse is over the box!";
        });

        document.getElementById("hover-box").addEventListener("mouseout", function() {
            document.getElementById("hover-message").innerText = "";
        });

        // Form Validation
        document.getElementById("user-form").addEventListener("submit", function(event) {
            event.preventDefault(); // Prevent form submission

            let name = document.getElementById("name").value;
            let email = document.getElementById("email").value;
            let isValid = true;

            // Validate Name
            if (name.length < 3) {
                document.getElementById("name-error").innerText = "Name must be at least 3 characters.";
                isValid = false;
            } else {
                document.getElementById("name-error").innerText = "";
            }

            // Validate Email
            if (!email.includes("@")) {
                document.getElementById("email-error").innerText = "Please enter a valid email.";
                isValid = false;
            } else {
                document.getElementById("email-error").innerText = "";
            }

            // If valid, submit
            if (isValid) {
                alert("Form submitted successfully!");
            }
        });
    </script>

</body>
</html>
