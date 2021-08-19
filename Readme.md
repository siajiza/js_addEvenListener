# **AddEvenListener**

### **How works addEvenListener**
_One of the most popular features of Javascript, is how we can implement dynamic behavior in to our app or website._

_We can find this "dynamic behavior" using a Javascript function named "addEvenListener" where we call some behavior where we for example can pass in the pointer on the text or click on it and we create some "dynamic behavior"._

**SYNTAX**

    target.addEventListener(type, listener);

The EventTarget method addEventListener() sets up a function that will be called whenever the specified event is delivered to the target. Common targets are Element, Document, and Window, but the target may be any object that supports events (such as XMLHttpRequest).

**_"addEventListener()"_** works by adding a function or an object that implements EventListener to the list of event listeners for the specified event type on the EventTarget on which it's called.

**------------------------------------------------------------**

Parameters:

* type

    An event to occur. Examples of an event are the user clicking or moving the mouse, pressing a key on the keyboard, disk I/O, network activity, or an internal timer or interrupt.


* listener

    The object that receives a notification (an object that implements the Event interface) when an event of the specified type occurs. This must be an object implementing the EventListener interface, or a **JavaScript function**

**------------------------------------------------------------**

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


