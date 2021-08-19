# **AddEvenListener**

One of the most popular features of Javascript, is how we can implement dynamic behavior in to our app or website.

We can find this "dynamic behavior" using a Javascript function named "addEvenListener" where we call some behavior where we for example can pass in the pointer on the text or click on it and we create some "dynamic behavior".

Let´s start with a basic practice!

## **Behavior**

we´re gonna build a "hover" (pass the cursor over the image) over two images where will appear a descriptive text.

### **CSS**

    <style>
    img {
        width: 100px;
    }
    .container {
        position: relative;
        text-align: center;
        color: white;
    }
    .show-img-overlay {
        position: relative;
        bottom: 60px;
        font-size: 21px;
        font-family: Arial, Helvetica, sans-serif;
    }
    .hide-img-overlay {
        position: relative;
        bottom: 60px;
        font-size: 21px;
        color: transparent;
    }
    </style>

### **HTML**

    <div class="container">
        <img src="https://s3.amazonaws.com/bottega-devcamp/browser-js/laptop.jpg" class="site-img" alt="Laptop">
        <div class="hide-img-overlay">Image Description</div>
    </div>

    <div class="container">
        <img src="https://s3.amazonaws.com/bottega-devcamp/browser-js/another-laptop.jpg" class="site-img" alt="Laptop">
        <div class="hide-img-overlay">Some Other Image Description</div>
    </div>

<div class="container">
    <img src="https://s3.amazonaws.com/bottega-devcamp/browser-js/laptop.jpg" class="site-img" alt="Laptop">
    <div class="hide-img-overlay">Image Description</div>
  </div>

  <div class="container">
    <img src="https://s3.amazonaws.com/bottega-devcamp/browser-js/another-laptop.jpg" class="site-img" alt="Laptop">
    <div class="hide-img-overlay">Some Other Image Description</div>
  </div>


## **JAVASCRIPT**

    <script>
        const img = document.getElementsByClassName('site-img')[0];
        img.addEventListener('click', (e) => {
            debugger;
        });
        const imgs = document.querySelectorAll('.site-img');
        imgs.forEach(img => {
            img.addEventListener('mouseover', (event) => {
            const captionElement = event.target.parentElement.children[1];
            captionElement.className = 'show-img-overlay';
            });
        });
        imgs.forEach(img => {
            img.addEventListener('mouseout', (event) => {
            const captionElement = event.target.parentElement.children[1];
            captionElement.className = 'hide-img-overlay';
            });
        });
    </script>


