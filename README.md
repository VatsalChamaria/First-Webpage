# First-Webpage
this is my webpage for front end development
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
    <script>
        const gallery = document.getElementById('gallery');
        const images = gallery.getElementsByTagName('img');

        // Toggle selection on image click
        for (let img of images) {
            img.addEventListener('click', function() {
                img.classList.toggle('selected');
            });
        }

        function selectAll() {
            for (let img of images) {
                img.classList.add('selected');
            }
        }

        function deselectAll() {
            for (let img of images) {
                img.classList.remove('selected');
            }
        }

        function alertSelected() {
            let count = 0;
            for (let img of images) {
                if (img.classList.contains('selected')) count++;
            }
            alert('Selected images: ' + count);
        }
    </script>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0 20px;
        }
        h1 {
            color: #333;
            text-align: center;
            margin-top: 30px;
        }
        h2 {
            color: #555;
            text-align: center;
            margin-bottom: 30px;
        }
        .image-gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }
        .image-gallery img {
            max-width: 250px;
            height: auto;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            background: #fff;
            padding: 8px;
            transition: transform 0.2s;
            cursor: pointer;
            width: 100%;
            box-sizing: border-box;
        }
        .image-gallery img.selected {
            border: 3px solid #0078d7;
            transform: scale(1.05);
        }
        .button-group {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
        }
        .button-group button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            background: #0078d7;
            color: #fff;
            cursor: pointer;
            transition: background 0.2s;
        }
        .button-group button:hover {
            background: #005fa3;
        }
        @media (max-width: 900px) {
            .image-gallery {
                gap: 15px;
            }
            .image-gallery img {
                max-width: 180px;
            }
        }
        @media (max-width: 600px) {
            body {
                padding: 0 5px;
            }
            h1, h2 {
                font-size: 1.3em;
            }
            .image-gallery {
                flex-direction: column;
                align-items: center;
                gap: 10px;
            }
            .image-gallery img {
                max-width: 95vw;
            }
            .button-group {
                flex-direction: column;
                gap: 10px;
            }
            .button-group button {
                width: 100%;
                font-size: 15px;
            }
        }
    </style>
<body>
    <h1>Main Heading</h1>
    <h2>Subheading</h2>
    
    <div class="button-group">
        <button onclick="selectAll()">Select All</button>
        <button onclick="deselectAll()">Deselect All</button>
        <button onclick="alertSelected()">Show Selected Count</button>
    </div>
    <div class="image-gallery" id="gallery">
        <img src="image.jpg" alt="Description of the image">
        <img src="photo1.jpg" alt="A scenic landscape">
        <img src="photo2.jpg" alt="Close-up of a flower">
        <img src="photo3.jpg" alt="City skyline at sunset">
    </div>
    
</body>
</html>
