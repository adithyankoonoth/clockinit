<html>
<head>
    <title>Alarm Clock</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom right, #fceabb, #f8b500);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background: white;
            border-radius: 20px;
            padding: 50px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #888;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .logo span {
            color: #000;
            margin-left: 5px;
        }
        .logo .am {
            background: #000;
            color: #fff;
            font-size: 12px;
            padding: 2px 5px;
            border-radius: 3px;
            margin-left: 5px;
        }
        .time {
            font-size: 96px;
            font-weight: bold;
            color: #000;
            margin: 20px 0;
        }
        .controls {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 20px;
        }
        .controls select {
            padding: 10px;
            font-size: 16px;
            border: 1px solid #000;
            border-radius: 5px;
            background: #fff;
        }
        .set-alarm {
            padding: 10px 20px;
            font-size: 16px;
            color: #fff;
            background: #000;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="logo">
            ALARM <span>CLOCK</span><div class="am">AM</div>
        </div>
        <div class="time" id="clock">08:54:44</div>
        <div class="controls">
            <select id="hours">
                <option>Hrs</option>
                <!-- Add hour options here -->
                <script>
                    for (let i = 0; i < 24; i++) {
                        document.write('<option value="' + i + '">' + (i < 10 ? '0' + i : i) + '</option>');
                    }
                </script>
            </select>
            <select id="minutes">
                <option>Min</option>
                <!-- Add minute options here -->
                <script>
                    for (let i = 0; i < 60; i++) {
                        document.write('<option value="' + i + '">' + (i < 10 ? '0' + i : i) + '</option>');
                    }
                </script>
            </select>
            <select id="seconds">
                <option>Sec</option>
                <!-- Add second options here -->
                <script>
                    for (let i = 0; i < 60; i++) {
                        document.write('<option value="' + i + '">' + (i < 10 ? '0' + i : i) + '</option>');
                    }
                </script>
            </select>
        </div>
        <button class="set-alarm" onclick="setAlarm()">Set Alarm</button>
    </div>

    <script>
        function updateTime() {
            const now = new Date();
            const hours = now.getHours().toString().padStart(2, '0');
            const minutes = now.getMinutes().toString().padStart(2, '0');
            const seconds = now.getSeconds().toString().padStart(2, '0');
            document.getElementById('clock').textContent = ${hours}:${minutes}:${seconds};
        }

        setInterval(updateTime, 1000);

        function setAlarm() {
            const hours = document.getElementById('hours').value;
            const minutes = document.getElementById('minutes').value;
            const seconds = document.getElementById('seconds').value;

            if (hours === 'Hrs' || minutes === 'Min' || seconds === 'Sec') {
                alert('Please select a valid time for the alarm.');
                return;
            }

            const alarmTime = ${hours}:${minutes}:${seconds};
            alert(Alarm set for ${alarmTime});
        }
    </script>
</body>
</html>
