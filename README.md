<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Timer (Ubaida to Jordan)</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            margin: 0;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background-image: url('https://cdn4.vectorstock.com/i/1000x1000/71/63/ducks-background-vector-10507163.jpg');
            background-size: cover;
            background-position: center;
            color: white; /* Text color to be white for better visibility */
            overflow: hidden;
        }

        h1 {
            font-size: 36px; /* Bigger font size for the title */
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8); /* Adding a shadow to the title */
            color: black; /* Text color for the title */
        }

        #countdown {
            font-size: 48px; /* Larger font size for the countdown */
            font-weight: bold;
            font-style: italic;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* Adding a subtle shadow */
            animation: moveText 2s ease-in-out infinite alternate; /* Add a moving animation */
            color: #ffcc00; /* Text color with a touch of yellow */
        }

        @keyframes moveText {
            from {
                transform: translateY(-10px);
            }
            to {
                transform: translateY(10px);
            }
        }
    </style>
</head>
<body>

<h1>The Timer (Ubaida to Jordan)</h1>
<div id="countdown"></div>

<script>
    // Set the target date and time (January 8, 2024, 13:00:00)
    const targetDate = new Date('2024-01-08T13:00:00').getTime();

    function updateCountdown() {
        const now = new Date().getTime();
        const timeRemaining = targetDate - now;

        // Calculate days, hours, minutes, and seconds
        const days = Math.floor(timeRemaining / (1000 * 60 * 60 * 24));
        const hours = Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000);

        // Display the countdown
        document.getElementById('countdown').innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;

        // If the countdown is over, display a message
        if (timeRemaining < 0) {
            clearInterval(countdownInterval);
            document.getElementById('countdown').innerHTML = 'Countdown finished!';
        }
    }

    // Update the countdown every second
    const countdownInterval = setInterval(updateCountdown, 1000);

    // Initial call to display the countdown immediately
    updateCountdown();
</script>

</body>
</html>
