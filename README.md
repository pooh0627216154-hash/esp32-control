<!DOCTYPE html>
<html>
<head>
    <title>ESP32 Global Control</title>
    <style>
        body { font-family: Arial; text-align: center; margin-top: 50px; }
        button {
            padding: 20px 40px;
            font-size: 25px;
            border-radius: 15px;
            margin: 10px;
        }
        .on { background: green; color: white; }
        .off { background: red; color: white; }
    </style>
</head>
<body>
    <h1>ESP32 Control Anywhere</h1>

    <button class="on" onclick="setLight(1)">TURN ON</button>
    <button class="off" onclick="setLight(0)">TURN OFF</button>

    <script>
        const url = "https://esp32-control-c6192-default-rtdb.asia-southeast1.firebasedatabase.app/light.json";

        function setLight(v) {
            fetch(url, {
                method: "PUT",
                body: JSON.stringify(v)
            });
        }
    </script>
</body>
</html>
