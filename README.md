# Ex.08 Design of Interactive Image Gallery
# Date:18/11/2024
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <style>
        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: radial-gradient(circle, #2b5876, #4e4376);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            color: #fff;
        }

        h1 {
            font-size: 3em;
            color: #ffdd59;
            font-weight: bold;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
            margin-bottom: 20px;
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: translateY(-20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 15px;
            width: 90%;
            max-width: 1200px;
            padding: 10px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.08);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease, filter 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.2);
            filter: brightness(0.7);
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6);
            color: #ffdd59;
            font-size: 1.2em;
            font-weight: bold;
            display: flex;
            justify-content: center;
            align-items: center;
            text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.5);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .overlay {
            opacity: 1;
        }

        .full-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }

        .full-screen img {
            max-width: 80%;
            max-height: 80%;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.8);
        }

        .full-screen.active {
            opacity: 1;
            visibility: visible;
        }

        .close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 2.5em;
            color: #ffdd59;
            cursor: pointer;
            background: none;
            border: none;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
            transition: color 0.3s ease;
        }

        .close-btn:hover {
            color: #fff;
        }
    </style>
</head>
<body>
    <h1>Image Gallery</h1>
    <div class="gallery" id="gallery">
       
    </div>

    <div class="full-screen" id="fullScreen">
        <button class="close-btn" id="closeBtn">&times;</button>
        <img id="fullScreenImg" src="" alt="Full View">
    </div>

    <script>
        const gallery = document.getElementById('gallery');
        const fullScreen = document.getElementById('fullScreen');
        const fullScreenImg = document.getElementById('fullScreenImg');
        const closeBtn = document.getElementById('closeBtn');

    
        const images = [
            's1.jpg',
            's2.jpg',
            's3.jpg',
            's4.jpg',
            's5.jpg',
            's6.png',
            's7.png',
            's8.png',
            's9.jpg',
            's1.jpg',
            's5.jpg',
            's8.png',
            

        ];

        
        images.forEach((src, index) => {
            const item = document.createElement('div');
            item.classList.add('gallery-item');

            const img = document.createElement('img');
            img.src = src;
            img.alt = `Image ${index + 1}`;

            const overlay = document.createElement('div');
            overlay.classList.add('overlay');
            overlay.innerText = `Image ${index + 1}`;

            item.appendChild(img);
            item.appendChild(overlay);
            gallery.appendChild(item);

            item.addEventListener('click', () => {
                fullScreenImg.src = src;
                fullScreen.classList.add('active');
            });
        });

        
        closeBtn.addEventListener('click', () => {
            fullScreen.classList.remove('active');
        });

        
        fullScreen.addEventListener('click', (e) => {
            if (e.target === fullScreen || e.target === closeBtn) {
                fullScreen.classList.remove('active');
            }
        });
    </script>
</body>
</html>

~~~
# OUTPUT:
![imagegallery](https://github.com/user-attachments/assets/54890127-550d-46fb-81a3-527c997413b3)

![galler](https://github.com/user-attachments/assets/1d2bfde1-7f65-4b76-905a-46ce9cd51d07)


# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
