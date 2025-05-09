# Ex.08 Design of Interactive Image Gallery
## Date:

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
```<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Image Gallery</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&family=Playfair+Display:wght@700&family=Quicksand:wght@500&display=swap" rel="stylesheet">
  <style>
    /* Global Reset */
    body {
      margin: 0;
      padding: 0;
      font-family: 'Quicksand', sans-serif;
      background: linear-gradient(45deg, #ff6b6b, #f06595, #ab83c8, #6a4c93, #ff9f1c);
      background-size: 400% 400%;
      animation: gradientAnimation 15s ease infinite;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      text-align: center;
    }

    @keyframes gradientAnimation {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }

    /* Title Styling */
    h1 {
      font-family: 'Playfair Display', serif;
      font-size: 4rem;
      color: #fff;
      text-shadow: 0 0 20px rgba(255, 255, 255, 0.8);
      margin-bottom: 50px;
      z-index: 1;
      animation: fadeIn 2s ease-in-out;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    /* Gallery Container */
    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 30px;
      max-width: 80%;
      margin: 0 auto;
      z-index: 1;
      animation: galleryFadeIn 1.5s ease-in-out;
    }

    @keyframes galleryFadeIn {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Gallery Item */
    .gallery-item {
      position: relative;
      overflow: hidden;
      border-radius: 15px;
      background: rgba(0, 0, 0, 0.5);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
      transition: transform 0.4s ease, box-shadow 0.4s ease;
    }

    .gallery-item:hover {
      transform: scale(1.05);
      box-shadow: 0 15px 30px rgba(0, 0, 0, 0.6);
    }

    .gallery-item img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 12px;
      transition: transform 0.3s ease;
    }

    .gallery-item h2 {
      position: absolute;
      bottom: 0;
      width: 100%;
      padding: 15px;
      font-size: 1.3rem;
      font-family: 'Poppins', sans-serif;
      background: rgba(0, 0, 0, 0.7);
      color: #fff;
      text-shadow: 0 0 5px rgba(0, 0, 0, 0.8);
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    /* Overlay Styling */
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.8);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s ease;
    }

    .overlay img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.8);
    }

    .overlay.active {
      opacity: 1;
      pointer-events: auto;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 30px;
      font-size: 2.5rem;
    

  <script>
    const galleryItems = document.querySelectorAll('.gallery-item img');
    const overlay = document.getElementById('overlay');
    const overlayImage = document.getElementById('overlayImage');
    const closeBtn = document.getElementById('close');

    galleryItems.forEach(item => {
      item.addEventListener('click', () => {
        overlayImage.src = item.src;
        overlay.classList.add('active');
      });
    });

    closeBtn.addEventListener('click', () => {
      overlay.classList.remove('active');
    });

    overlay.addEventListener('click', (e) => {
      if (e.target === overlay) {
        overlay.classList.remove('active');
      }
    });
  </script>

</body>
</html>
```

## OUTPUT:
![Screenshot 2025-05-09 132231](https://github.com/user-attachments/assets/fa563f75-2435-4515-9b01-adeaf6ff90f9)

![image](https://github.com/user-attachments/assets/1db227f6-ac76-44e1-9ccb-b8418585cfe3)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
