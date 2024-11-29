# Ex.08 Design of Interactive Image Gallery
## Date:
23/10/24
## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
HTML :
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Photo Gallery</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1> Lucifer's Gallery </h1>
    <div class="gallery">
        <img src= "andromeda-galaxy.jpg" alt="ANDROMEDA - GALAXY" class="gallery-item">
        <img src= "austinchalk_T2_anime_film_T-800_sitting_on_a_motorcycle_90s_ani_08fc9a01-59c7-47d2-bf0f-15dccf8540d0.png" alt="ANIME MOTORCYCLE" class="gallery-item">
        <img src= "b-008.jpg" alt="TOKYO" class="gallery-item">
        <img src= "mima.png" alt="BEAUTY" class="gallery-item">
        <img src= "tiredgod.png" alt="SILVER SUFER" class="gallery-item">
        <img src= "wallpaperflare.com_wallpaper.jpg" alt="NYC" class="gallery-item">
        <img src= "what.png" alt="WOW" class="gallery-item">
        <img src= "2025-Porsche-911-Carrera-GTS-003-2160.jpg" alt="SEXY LADY" class="gallery-item">
        <img src= "Wake up dadd's home___.jpg" alt="DADDY'S HOME" class="gallery-item">
        <img src= "bisbiswas-lit-up-sky.jpg" alt="ME & WHO ?" class="gallery-item">
        
    </div>

    
    <div id="lightbox" class="lightbox">
        <span class="close">&times;</span>
        <img class="lightbox-content" id="lightbox-img">
        <div id="caption"></div>
        <a class="prev">&#10094;</a>
        <a class="next">&#10095;</a>
    </div>

    <script src="script.js"></script>
</body>
</html>

```
CSS : 
```
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: rgb(185, 142, 210);
}

h1 {
    color: #333;
    font-family: fantasy;
    font-style: italic;
    position: center;
    margin-top: 30px    ;
}

.gallery {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

.gallery-item {
    width: 200px;
    margin: 10px;
    cursor: pointer;
    transition: transform 0.3s;
}

.gallery-item:hover {
    transform: scale(1.1);
}

/* Lightbox/Modal */
.lightbox {
    display: none;
    position: fixed;
    z-index: 1;
    padding-top: 100px;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
}

.lightbox-content {
    margin: auto;
    display: block;
    max-width: 90%;
    max-height: 80%;
}

.close {
    position: absolute;
    top: 20px;
    right: 35px;
    color: #fff;
    font-size: 40px;
    font-weight: bold;
    cursor: pointer;
}

#caption {
    text-align: center;
    color: #fff;
    padding: 10px 0;
}

/* Navigation buttons (prev/next) */
.prev, .next {
    cursor: pointer;
    position: absolute;
    top: 50%;
    width: auto;
    padding: 16px;
    margin-top: -50px;
    color: white;
    font-weight: bold;
    font-size: 24px;
    transition: 0.3s ease;
    user-select: none;
}

.prev {
    left: 10px;
}

.next {
    right: 10px;
}

.prev:hover, .next:hover {
    color: #f1f1f1;
}

```
JAVASCRIPT : 
```
const galleryItems = document.querySelectorAll('.gallery-item');
const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightbox-img');
const captionText = document.getElementById('caption');
const closeBtn = document.querySelector('.close');
const nextBtn = document.querySelector('.next');
const prevBtn = document.querySelector('.prev');

let currentIndex = 0;

function openLightbox(index) {
    lightbox.style.display = 'block';
    lightboxImg.src = galleryItems[index].src;
    captionText.innerHTML = galleryItems[index].alt;
    currentIndex = index;
}

closeBtn.addEventListener('click', function () {
    lightbox.style.display = 'none';
});

nextBtn.addEventListener('click', function () {
    currentIndex = (currentIndex + 1) % galleryItems.length; 
    openLightbox(currentIndex);
});

prevBtn.addEventListener('click', function () {
    currentIndex = (currentIndex - 1 + galleryItems.length) % galleryItems.length; 
    openLightbox(currentIndex);
});

galleryItems.forEach((item, index) => {
    item.addEventListener('click', function () {
        openLightbox(index);
    });
});

```
## OUTPUT:
![Screenshot (25)](https://github.com/user-attachments/assets/e3b6373b-40dc-4d91-9663-2e7c8aaea2ab)
![Screenshot (26)](https://github.com/user-attachments/assets/e33102d0-9265-4c5b-ac38-cddfdfbd4976)
![Screenshot (27)](https://github.com/user-attachments/assets/49822581-d118-4d5e-afa4-adbf9623b521)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
