```html

<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <title>Analog Clock</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #000;
        }

        .clock {
            width: 300px;
            height: 300px;
            margin: 100px auto;
            border: 10px solid #fff;
            border-radius: 50%;
            position: relative;
        }

        .clock-face {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            background-color: #fff;
            border-radius: 50%;
        }

        .clock-numbers {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 20px;
            font-weight: bold;
        }

        .clock-numbers li {
            position: absolute;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: #000;
            list-style-type: none;
        }

        .clock-numbers li:nth-child(1) {
            top: 0;
            left: 45%;
        }

        .clock-numbers li:nth-child(2) {
            top: 10%;
            left: 55%;
        }

        .clock-numbers li:nth-child(3) {
            top: 19%;
            left: 62%;
        }

        .clock-numbers li:nth-child(4) {
            top: 26%;
            left: 69%;
        }

        .clock-numbers li:nth-child(5) {
            top: 31%;
            left: 75%;
        }

        .clock-numbers li:nth-child(6) {
            top: 35%;
            left: 80%;
        }

        .clock-numbers li:nth-child(7) {
            top: 38%;
            left: 85%;
        }

        .clock-numbers li:nth-child(8) {
            top: 40%;
            left: 89%;
        }

        .clock-numbers li:nth-child(9) {
            top: 41%;
            left: 93%;
        }

        .clock-numbers li:nth-child(10) {
            top: 41%;
            left: 97%;
        }

        .clock-numbers li:nth-child(11) {
            top: 40%;
            left: 101%;
        }

        .clock-numbers li:nth-child(12) {
            top: 38%;
            left: 105%;
        }

        .clock-hand {
            position: absolute;
            top: 50%;
            left: 50%;
            transform-origin: bottom;
            transform: translate(-50%, -50%);
        }

        .clock-hand:nth-child(1) {
            width: 2px;
            height: 70px;
            background-color: #000;
        }

        .clock-hand:nth-child(2) {
            width: 4px;
            height: 50px;
            background-color: #000;
        }

        .clock-hand:nth-child(3) {
            width: 1px;
            height: 100px;
            background-color: #f00;
        }
    </style>
</head>
<body>
    <div class="clock">
        <div class="clock-face">
            <ol class="clock-numbers">
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
            </ol>
        </div>
        <div class="clock-hand hour"></div>
        <div class="clock-hand minute"></div>
        <div class="clock-hand second"></div>
    </div>

    <script>
        const clock = document.querySelector('.clock');
        const hourHand = clock.querySelector('.hour');
        const minuteHand = clock.querySelector('.minute');
        const secondHand = clock.querySelector('.second');

        const setDate = () => {
            const now = new Date();

            const seconds = now.getSeconds();
            const minutes = now.getMinutes();
            const hours = now.getHours();

            const secondsDegrees = ((seconds / 60) * 360) + 90;
            const minutesDegrees = ((minutes / 60) * 360) + 90;
            const hoursDegrees = ((hours / 12) * 360) + 90;

            secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
            minuteHand.style.transform = `rotate(${minutesDegrees}deg)`;
            hourHand.style.transform = `rotate(${hoursDegrees}deg)`;
        }

        setInterval(setDate, 1000);
    </script>
</body>
</html>

```