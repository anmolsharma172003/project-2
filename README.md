<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Slider</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f2f2f2;
            font-family: Arial, sans-serif;
        }
        .slider {
            width: 800px;
            height: 500px;
            overflow: hidden;
            border-radius: 10px;
            position: relative;
        }
        .slides {
            width: 500%;
            height: 100%;
            display: flex;
        }
        .slide {
            width: 20%;
            transition: 0.6s ease;
        }
        .slide img {
            width: 100%;
            height: 100%;
            border-radius: 10px;
        }
        .navigation-manual {
            position: absolute;
            width: 800px;
            margin-top: -40px;
            display: flex;
            justify-content: center;
        }
        .manual-btn {
            border: 2px solid #ffffff;
            padding: 5px;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.4s;
        }
        .manual-btn:not(:last-child) {
            margin-right: 40px;
        }
        .manual-btn:hover {
            background-color: #ffffff;
        }
        #radio1:checked ~ .first {
            margin-left: 0;
        }
        #radio2:checked ~ .first {
            margin-left: -20%;
        }
        #radio3:checked ~ .first {
            margin-left: -40%;
        }
        #radio4:checked ~ .first {
            margin-left: -60%;
        }
        .navigation-auto {
            position: absolute;
            width: 800px;
            display: flex;
            justify-content: center;
            margin-top: -80px;
        }
        .navigation-auto div {
            border: 2px solid #ffffff;
            padding: 5px;
            border-radius: 10px;
            transition: 0.4s;
        }
        .navigation-auto div:not(:last-child) {
            margin-right: 40px;
        }
        #radio1:checked ~ .navigation-auto .auto-btn1 {
            background-color: #ffffff;
        }
        #radio2:checked ~ .navigation-auto .auto-btn2 {
            background-color: #ffffff;
        }
        #radio3:checked ~ .navigation-auto .auto-btn3 {
            background-color: #ffffff;
        }
        #radio4:checked ~ .navigation-auto .auto-btn4 {
            background-color: #ffffff;
        }
    </style>
</head>
<body>
    <div class="slider">
        <div class="slides">
            <!-- Radio buttons for navigation -->
            <input type="radio" name="radio-btn" id="radio1">
            <input type="radio" name="radio-btn" id="radio2">
            <input type="radio" name="radio-btn" id="radio3">
            <input type="radio" name="radio-btn" id="radio4">

            <!-- Slide images -->
            <div class="slide first">
                <img src="image1.jpg" alt="Image 1">
            </div>
            <div class="slide">
                <img src="image2.jpg" alt="Image 2">
            </div>
            <div class="slide">
                <img src="image3.jpg" alt="Image 3">
            </div>
            <div class="slide">
                <img src="image4.jpg" alt="Image 4">
            </div>

            <!-- Automatic navigation -->
            <div class="navigation-auto">
                <div class="auto-btn1"></div>
                <div class="auto-btn2"></div>
                <div class="auto-btn3"></div>
                <div class="auto-btn4"></div>
            </div>
        </div>

        <!-- Manual navigation -->
        <div class="navigation-manual">
            <label for="radio1" class="manual-btn"></label>
            <label for="radio2" class="manual-btn"></label>
            <label for="radio3" class="manual-btn"></label>
            <label for="radio4" class="manual-btn"></label>
        </div>
    </div>

    <script>
        let counter = 1;
        setInterval(() => {
            document.getElementById('radio' + counter).checked = true;
            counter++;
            if (counter > 4) {
                counter = 1;
            }
        }, 5000); 
    </script>
</body>
</html>
