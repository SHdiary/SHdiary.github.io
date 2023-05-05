# SHdiary.github.io
<!DOCTYPE html>
<html>
<head>
    <style>
        .thumbnail {
            width: 100px;
            height: 100px;
            margin: 10px;
            transition: transform 0.5s;
        }
        .thumbnail:hover {
            transform: scale(1.2);
        }
        .background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            transition: opacity 1s;
            background-size: cover;
        }
        .foreground {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 36px;
        }
        .thumbnails {
            display: flex;
            justify-content: center;
        }
        @media (max-width: 600px) {
            .thumbnail {
                width: 50px;
                height: 50px;
                margin: 5px;
            }
            .foreground {
                font-size: 18px;
            }
        }
    </style>
    <script>
        const messages = [
            "Message for image1",
            "Message for image2",
            "Message for image3",
            "Message for image4",
            "Message for image5"
        ];
        function changeBackground(imageUrl, index) {
    const background = document.querySelector('.background');
    const newBackground = background.cloneNode(true);
    newBackground.style.backgroundImage = `url(${imageUrl})`;
    newBackground.style.opacity = 0;
    background.parentNode.insertBefore(newBackground, background);
    setTimeout(() => {
        newBackground.style.opacity = 1;
        background.style.opacity = 0;
        document.querySelector('.foreground').textContent = messages[index];
    }, 0);
    setTimeout(() => {
        background.remove();
    }, 1000);
}
    </script>
</head>
<body>
    <h1>1st Year Diary</h1>
    <div class="background"></div>
    <div class="foreground">Happy Anniversary Shreya</div>
    <div class="thumbnails">
        <img class="thumbnail" src="Papa.jpg" onclick="changeBackground('Papa.jpg', 0)">
        <img class="thumbnail" src="Mummy.jpg" onclick="changeBackground('Mummy.jpg', 1)">
        <img class="thumbnail" src="Papa.jpg" onclick="changeBackground('Papa.jpg', 2)">
        <img class="thumbnail" src="Mummy.jpg" onclick="changeBackground('Mummy.jpg', 3)">
        <img class="thumbnail" src="Papa.jpg" onclick="changeBackground('Papa.jpg', 4)">
    </div>
</body>
</html>
