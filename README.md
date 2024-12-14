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
    <title>Gallery</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f9f9f9;
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
            height: 100vh;
        }

        .heading {
            text-align: center;
            margin: 20px 0;
        }

        .gallery-container {
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            margin: 20px auto;
            max-width: 90%;
            height: 500px;
            background: white;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .gallery-images {
            display: flex;
            transition: transform 0.5s ease;
            max-width: 100%;
        }

        .gallery-images img {
            width: 400px;
            height: 300px;
            object-fit: cover;
            margin: 0 10px;
        }

        .btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(0, 0, 0, 0.5);
            color: white;
            font-size: 20px;
            border: none;
            cursor: pointer;
            padding: 10px;
        }

        .prev-btn {
            left: 10px;
        }

        .next-btn {
            right: 10px;
        }

        .btn:hover {
            background: rgba(0, 0, 0, 0.8);
        }
    </style>
</head>
<body>

<div class="heading">
    <h1>Gallery</h1>
    <h2>Switzerland</h2>
</div>
<div class="gallery-container">
    <div class="gallery-images">
        <img src="s1.jpg" alt="Image 1">
        <img src="s2.jpg" alt="Image 2">
        <img src="s3.jpg" alt="Image 3">
        <img src="s4.jpg" alt="Image 4">
        <img src="s5.jpg" alt="Image 5">
        <img src="s6.png" alt="Image 6">
        <img src="s7.png" alt="Image 7">
        <img src="s8.png" alt="Image 8">
        <img src="s9.jpg" alt="Image 9">
    </div>

    <button class="btn prev-btn" onclick="moveSlide('prev')">&#10094;</button>
    <button class="btn next-btn" onclick="moveSlide('next')">&#10095;</button>
</div>

<script>
    let currentSlide = 0; 
    function moveSlide(direction) {
        const slides = document.querySelectorAll('.gallery-images img');
        const totalSlides = slides.length;

        if (direction === 'next') {
            currentSlide = (currentSlide + 1) % totalSlides;
        } else if (direction === 'prev') {
            currentSlide = (currentSlide - 1 + totalSlides) % totalSlides;
        }
        const gallery = document.querySelector('.gallery-images');
        gallery.style.transform = `translateX(-${currentSlide * (slides[0].offsetWidth + 20)}px)`;
    }
</script>

</body>
</html>

~~~
# OUTPUT:
![gallery1](https://github.com/user-attachments/assets/a6047fca-675c-4352-9cc9-334d7e119d3d)

![gallery2](https://github.com/user-attachments/assets/13f46dab-b1cd-4cf6-a22c-f2598050fd3a)

# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
