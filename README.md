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
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gallery Page</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: white;
      color:blueviolet;
      margin: 0;
      padding: 20px;
      text-align: center;
    }

    h2 {
      font-size: 22px;
      letter-spacing: 1px;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(8, 1fr); 
      gap: 5px; 
      margin-top: 20px;
      padding: 0;
      width: 100%;
    }

    .gallery img {
      width: 100%;       
      height: 800px;     
      object-fit: cover; 
      border: 5px solid maroon; 
      border-radius: 5px; 
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
    }

    .gallery img:hover {
      transform: scale(1.05);
      box-shadow: 0 0 15px black;
      border-color:plum;
    }

    .lightbox {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.9);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .lightbox img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 10px;
      animation: zoomIn 0.3s ease;
      box-shadow: 0 0 25px black;
      border: 5px solid maroon; 
    }

    @keyframes zoomIn {
      from {
        transform: scale(0.8);
        opacity: 0;
      }
      to {
        transform: scale(1);
        opacity: 1;
      }
    }

    .close {
      position: absolute;
      top: 20px;
      right: 30px;
      font-size: 40px;
      font-weight: bold;
      color: plum;
      cursor: pointer;
      transition: color 0.2s;
    }

    .close:hover {
      color: red;
    }

    @media (max-width: 1600px) {
      .gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
      }

      .gallery img {
        flex: 0 0 auto;
        width: 18%; 
        height:700px;
      }
    }
  </style>
</head>
<body>

  <h2><b>GALLERY PAGE</b></h2>

  <div class="gallery">
    <img src="cat1.webp" alt="img1" onclick="openLightbox(this)">
    <img src="cat2.png" alt="img2" onclick="openLightbox(this)">
    <img src="cat3.jpg" alt="img3" onclick="openLightbox(this)">
    <img src="cat4.jpg" alt="img4" onclick="openLightbox(this)">
    <img src="cat5.webp" alt="img5" onclick="openLightbox(this)">
    
  </div>

  <div class="lightbox" id="lightbox">
    <span class="close" onclick="closeLightbox()">&times;</span>
    <img id="lightbox-img" src="">
  </div>

  <script>
    var lightbox = document.getElementById("lightbox");
    var lightboxImg = document.getElementById("lightbox-img");

    function openLightbox(image) {
      lightbox.style.display = "flex";
      lightboxImg.src = image.src;
    }

    function closeLightbox() {
      lightbox.style.display = "none";
    }

    lightbox.addEventListener('click', function(e) {
      if (e.target === lightbox) {
        closeLightbox();
      }
    });
  </script>

</body>
</html>
```
## OUTPUT:
<img width="910" height="472" alt="image" src="https://github.com/user-attachments/assets/78b4935e-2cd4-49cc-b1fe-dd31f72a85f4" />
![Uploading image.png…]()


## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
