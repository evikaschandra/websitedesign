<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soulmate Name Generator</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            text-align: center;
            margin: 50px;
            user-select: none; /* Disable text selection */
            background: url('https://img.freepik.com/free-vector/valentine-background-with-hearts-design_1048-9804.jpg') no-repeat center center fixed;
            background-size: cover;
            color: #ff4081;
        }
        input, button, select {
            margin: 10px;
            padding: 10px;
            font-size: 18px;
            border: 2px solid #ff4081;
            border-radius: 10px;
        }
        button {
            background-color: #ff4081;
            color: white;
            cursor: pointer;
        }
        h1 {
            font-size: 40px;
            text-shadow: 3px 3px 5px rgba(255, 64, 129, 0.7);
        }
        h2 {
            font-size: 30px;
            text-shadow: 2px 2px 4px rgba(255, 64, 129, 0.7);
        }
    </style>
    <script>
        document.addEventListener('contextmenu', event => event.preventDefault()); // Disable right-click
        document.addEventListener('keydown', function(event) {
            if (event.ctrlKey && (event.key === 'u' || event.key === 's' || event.key === 'c' || event.key === 'j' || event.key === 'i')) {
                event.preventDefault();
            }
        }); // Disable common inspect element shortcuts
    </script>
</head>
<body>
    <h1>💖 Find Your Soulmate! 💖</h1>
    <p>Enter your name and gender to discover your soulmate's name! 💘</p>
    
    <input type="text" id="userName" placeholder="Enter your name">
    <select id="gender">
        <option value="male">Male</option>
        <option value="female">Female</option>
    </select>
    <button onclick="generateSoulmate()">💞 Find My Soulmate 💞</button>
    
    <h2 id="result"></h2>
    
    <script>
        (function() {
            function generateSoulmate() {
                const userName = document.getElementById('userName').value.trim();
                const gender = document.getElementById('gender').value;
                const result = document.getElementById('result');
                
                if (!userName) {
                    result.innerText = "Please enter your name!";
                    return;
                }
                
                const fixedNames = { "shikha": "Vikas" };
                if (fixedNames[userName.toLowerCase()]) {
                    result.innerText = `💖 Your soulmate is: ${fixedNames[userName.toLowerCase()]} 💖`;
                    return;
                }
                
                const maleNames = ["Rahul", "Amit", "Siddharth", "Arjun", "Rohan", "Kunal"];
                const femaleNames = ["Priya", "Neha", "Sneha", "Pooja", "Anjali", "Ritika"];
                
                const randomName = gender === "male" 
                    ? femaleNames[Math.floor(Math.random() * femaleNames.length)] 
                    : maleNames[Math.floor(Math.random() * maleNames.length)];
                
                result.innerText = `💖 Your soulmate is: ${randomName} 💖`;
            }
            
            window.generateSoulmate = generateSoulmate;
        })();
    </script>
</body>
</html>
