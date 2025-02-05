<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Image Slider</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #000;
        }
        .slider {
            position: relative;
            width: 60%;
            height: 400px;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
          .slide {
            position: absolute;
            width: 60%;
            height: 100%;
            transition: transform 0.6s ease, opacity 0.6s ease;
            opacity: 0;
            transform: scale(0.8);
            text-align: center;
        }
        .slide img {
            width: 100%;
            height: 100%;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }
        .slide.active {
            opacity: 1;
            transform: scale(1);
            z-index: 2;
        }
        .prev, .next {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(0, 0, 0, 0.6);
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 24px;
            cursor: pointer;
            z-index: 3;
        }
        .prev { left: 5%; }
        .next { right: 5%; }
        .caption {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(0, 0, 0, 0.5);
            padding: 15px 30px;
            color: white;
            border-radius: 8px;
        }
        .caption h2 {
            font-size: 24px;
        }
        .caption p {
            font-size: 18px;
            margin: 5px 0;
        }
        .caption span {
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="slider">
        <div class="slide active">
            <img src="C:\Users\pavan\Downloads\download1.jpeg" alt="Machu Picchu">
            <div class="caption">
                <h2>MACHU PICCHU</h2>
                <p>— PERU</p>
                <span>Adventure is never far away</span>
            </div>
        </div>
        <div class="slide">
            <img src="C:\Users\pavan\OneDrive\Pictures\133720022056446036.jpg" alt="Mountain View">
        </div>
        <div class="slide">
            <img src="C:\Users\pavan\Downloads\download2.jpeg" alt="Another Mountain">
        </div>
        <button class="prev">&#10094;</button>
        <button class="next">&#10095;</button>
    </div>
    <script>
        let slides = document.querySelectorAll(".slide");
        let index = 0;
        document.querySelector(".next").addEventListener("click", function() {
            slides[index].classList.remove("active");
            index = (index + 1) % slides.length;
            slides[index].classList.add("active");
        });
        document.querySelector(".prev").addEventListener("click", function() {
            slides[index].classList.remove("active");
            index = (index - 1 + slides.length) % slides.length;
            slides[index].classList.add("active");
        });
    </script>

</body>
</html>



