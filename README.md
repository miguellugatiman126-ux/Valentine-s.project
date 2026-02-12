<!DOCTYPE html>
<html lang="en">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine Mobile</title>
    <style>
        /* This makes the background pretty and centers everything */
        body { 
            background: linear-gradient(#ffdae0, #ffb6c1); 
            height: 100vh; 
            margin: 0; 
            display: flex; 
            flex-direction: column; 
            align-items: center; 
            justify-content: center; 
            overflow: hidden; /* Prevents scrolling when the button jumps */
            font-family: 'Comic Sans MS', cursive, sans-serif;
        }
        h1 { color: #d63384; font-size: 1.8rem; padding: 10px; }
        .btn-container { position: relative; width: 100%; height: 200px; }
        
        button { 
            font-size: 18px; 
            padding: 12px 25px; 
            border-radius: 50px; 
            border: none; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            position: absolute; /* Needed for the jumping effect */
        }

        #yesBtn { 
            background-color: #4CAF50; color: white; 
            left: 20%; top: 50%; transform: translate(-50%, -50%);
        }

        #noBtn { 
            background-color: #f44336; color: white; 
            left: 70%; top: 50%; transform: translate(-50%, -50%);
            transition: 0.1s; /* Makes the jump feel snappy */
        }
    </style>
</head>
<body>

    <h1>Will you be my Valentine? 💖</h1>
    <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueXpsZ2sybm5uZWZ3eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/MDJ9IbxxvDUQM/giphy.gif" width="200">

    <div class="btn-container">
        <button id="yesBtn" onclick="celebrate()">Yes</button>
        <button id="noBtn" ontouchstart="moveButton()" onmouseover="moveButton()">No</button>
    </div>

    <script>
        function moveButton() {
            const noBtn = document.getElementById('noBtn');
            // We subtract 100 to keep the button from going off the screen edge
            const x = Math.random() * (window.innerWidth - 100);
            const y = Math.random() * (window.innerHeight - 100);
            
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
        }

        function celebrate() {
            document.body.innerHTML = `
                <h1 style="margin-top:50px">I KNEW IT! ❤️</h1>
                <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2Zic3RndXNxcXp4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/c76IJLufpNwSULPk2m/giphy.gif" width="300">
                <p style="font-size: 20px; color: #d63384;">See you on Feb 14th!</p>
            `;
        }
    </script>
</body>
</html>
