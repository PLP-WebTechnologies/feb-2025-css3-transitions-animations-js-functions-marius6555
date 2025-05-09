# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Transitions & LocalStorage</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <button id="actionButton">Click Me!</button>
  <script>
    // Function to store user preferences in localStorage
    function storeUserPreference(key, value) {
      localStorage.setItem(key, value);
    }

    // Function to get user preferences from localStorage
    function getUserPreference(key) {
      return localStorage.getItem(key);
    }

    // Trigger animation when the page loads or when a user clicks the button
    window.onload = function() {
      const button = document.getElementById("actionButton");
      
      // Retrieve animation preference from localStorage
      if (!getUserPreference("buttonAnimated")) {
        // Add fade-in class to trigger the animation
        button.classList.add("fade-in");
        storeUserPreference("buttonAnimated", true);
      }

      // Event listener to store user preference on click
      button.addEventListener("click", function() {
        alert("Button clicked! Animating...");
      });
    };
  </script>
</body>
</html>
/* Base styles */
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f4f4f4;
}

button {
  padding: 15px 30px;
  font-size: 16px;
  border: none;
  background-color: #4CAF50;
  color: white;
  cursor: pointer;
  border-radius: 5px;
  transition: transform 0.3s ease, opacity 0.5s ease-in-out;
  opacity: 0;
  transform: translateY(20px);
}

button:hover {
  transform: translateY(-5px);
  background-color: #45a049;
}

/* Animation to fade in the button */
.fade-in {
  animation: fadeIn 1s forwards;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}


Happy Coding! 💻✨
