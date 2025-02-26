<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For You, My Love</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background: url('https://scontent.fmnl33-2.fna.fbcdn.net/v/t1.15752-9/481156118_1323558908790936_3788110898679596636_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=9f807c&_nc_eui2=AeFnpi1LeNOKd_k7s9N_EBfp4lOs1Qq4XtfiU6zVCrhe15BjUqRgRGYI_I3N_JmB3O2XSWafIpJjMoBO1FXuRIr8&_nc_ohc=fg8DywLaVDMQ7kNvgFyKKMQ&_nc_oc=AdjITyeMHBPtrnraaFb8MdoSAbv1B-mIXtgy37elKGOWSf7QNOJNlYcj8vVYhjRurYw&_nc_zt=23&_nc_ht=scontent.fmnl33-2.fna&oh=03_Q7cD1gHiVin3D86eSkMViq58m9toXYALsMs6JNZmRVWL2oZ96A&oe=67E6989B') no-repeat center center fixed;
            background-size: cover;
            color: pink;
            text-align: center;
            height: 150vh;
        }

        .container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100%;
        }

        header {
            font-size: 6em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }

        .heart {
            font-size: 8em;
            color: #ff4c4c;
            animation: heartbeat 1s infinite;
        }

        @keyframes heartbeat {
            0% {
                transform: scale(1);
            }
            25% {
                transform: scale(1.1);
            }
            50% {
                transform: scale(1);
            }
            75% {
                transform: scale(1.1);
            }
            100% {
                transform: scale(1);
            }
        }

        .message {
            font-size: 1.5em;
            margin-top: 20px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
            display: none; /* Hidden by default */
        }

        .love-time {
            font-size: 1.3em;
            font-weight: bold;
            margin-top: 20px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
            color: #ff4c4c;
        }

        .timer {
            font-size: 2em;
            margin-top: 20px;
            color: #ff4c4c;
            font-weight: bold;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
        }

        footer {
            position: absolute;
            bottom: 10px;
            font-size: 1.2em;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
        }

        .button {
            margin-top: 30px;
            padding: 15px 30px;
            font-size: 1.2em;
            background-color: #ff4c4c;
            color: white;
            text-decoration: none;
            border-radius: 30px;
            box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease-in-out;
            cursor: pointer;
        }

        .button:hover {
            background-color: #ff1f1f;
            transform: scale(1.1);
        }

    </style>
</head>
<body>

    <div class="container">
        <header>
            for my one and only baby
        </header>

        <div class="heart"> ♡ </div>

        <div class="message" id="hidden-message">
            My love, [Her Name],<br>
            Every moment with you is a beautiful adventure. You are my everything.
        </div>

        <div class="love-time" id="love-time">
            Loving you since: <span id="time-running"></span>
        </div>

        <!-- Button to reveal the message -->
        <button class="button" id="reveal-button">can you open it, babyy? 🥺</button>

        <div class="timer" id="timezone-time">
            Current Time in Philippines: <span id="philippines-time"></span>
        </div>

        <footer>
             made with love by your beb, maemae hehe
        </footer>
    </div>

    <script>
        // Replace this with the actual date you started your relationship
        const startDate = new Date("2023-01-18");

        // Function to calculate and display the time since you started the relationship
        function calculateTime() {
            const now = new Date();
            const diff = now - startDate;

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const years = Math.floor(days / 365);
            const months = Math.floor((days % 365) / 30);
            const remainingDays = days % 30;

            document.getElementById("time-running").textContent = `${years} years, ${months} months, ${remainingDays} days`;
        }

        // Function to display the current time in the Philippines (Asia/Manila)
        function updateTimezone() {
            const options = {
                timeZone: "Asia/Manila",  // Use 'Asia/Manila' for Philippines time
                hour: "2-digit",
                minute: "2-digit",
                second: "2-digit",
                hour12: true,
            };
            const formatter = new Intl.DateTimeFormat([], options);
            const timeString = formatter.format(new Date());
            document.getElementById("philippines-time").textContent = timeString;
        }

        // Show hidden message when the button is clicked
        document.getElementById("reveal-button").addEventListener("click", function() {
            const message = document.getElementById("hidden-message");
            message.style.display = "block";  // Reveal the hidden message
        });

        // Initial call to update the relationship time and timezone time
        calculateTime();
        updateTimezone();

        // Update the times every second
        setInterval(calculateTime, 1000);
        setInterval(updateTimezone, 1000);
    </script>
</body>
</html>
