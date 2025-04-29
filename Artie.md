<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ali Art Gallery</title>

  <style>
    body {
      font-family: 'Poppins', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f1f9ff;
      color: #333;
    }

    header,
    footer {
      background-color: #ff6f91;
      color: white;
      text-align: center;
      padding: 1.5rem 1rem;
    }

    nav a {
      margin: 0 1rem;
      color: #ffffff;
      font-weight: 600;
      text-decoration: none;
    }

    nav a:hover {
      text-decoration: underline;
    }

    .container {
      padding: 2rem;
      max-width: 1100px;
      margin: auto;
    }

    h2 {
      border-bottom: 3px solid #6bc8c7;
      padding-bottom: 0.5rem;
      margin-bottom: 1.5rem;
      color: #3d6b66;
    }

    .slider-container {
      position: relative;
      width: 100%;
      max-width: 1100px;
      margin: auto;
      overflow: hidden;
    }

    .slider {
      display: flex;
      transition: transform 0.5s ease;
    }

    .product {
      flex: 0 0 33.33%;
      padding: 1rem;
      text-align: center;
      background-color: #fff;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
      transition: transform 0.3s ease;
    }

    .product:hover {
      transform: translate(-6px);
    }

    .product img {
      max-width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 10px;
    }

    .product h3 {
      margin: 1rem 0;
      font-size: 1.2rem;
      color: #3d6b66;
    }

    .product p {
      color: #ff6f91;
      font-weight: bold;
    }

    .btn {
      display: inline-block;
      margin-top: 12px;
      padding: 0.6rem 1.2rem;
      background-color: #6bc8c7;
      color: white;
      font-weight: bold;
      text-decoration: none;
      border-radius: 6px;
      transition: background-color 0.3s;
    }

    .btn:hover {
      background-color: #5ba99e;
    }

    .prev,
    .next {
      position: absolute;
      top: 50%;
      transform: translate(-50%);
      background-color: rgba(0, 0, 0, 0.5);
      color: white;
      border: none;
      padding: 10px;
      cursor: pointer;
      font-size: 18px;
      border-radius: 50%;
    }

    .prev {
      left: 10px;
    }

    .next {
      right: 10px;
    }

    form input,
    form textarea,
    form button {
      display: block;
      width: 100%;
      padding: 0.75rem;
      margin-bottom: 1rem;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-family: inherit;
    }

    form button {
      background-color: #ff6f91;
      color: white;
      font-weight: bold;
      cursor: pointer;
      border: none;
    }

    form button:hover {
      background-color: #e85c7a;
    }
  </style>
</head>

<body>
  <header>
    <h1>Ali Art Gallery</h1>
    <nav>
      <a href="#home">Home</a>
      <a href="#products">Products</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section id="home" class="container">
    <h2>Welcome to Ali Art Gallery</h2>
    <p>Discover unique handmade crafts made with love and passion. Each item is created to bring charm and elegance into your home or as a gift.</p>
  </section>

  <section id="products" class="container">
    <h2>Our Products</h2>
    <div class="slider-container">
      <div class="slider">
        <div class="product">
          <img src="images/product1.jpg" alt="Product 1" />
          <h3>4 inch coaster</h3>
          <p>Price: PKR 800</p>
          <a class="btn" href="https://www.instagram.com/ali.art.53?igsh=dmRvNXkyYmV1cW82" target="_blank">Order on Instagram</a>
        </div>
        <div class="product">
          <img src="images/product2.jpg" alt="Product 2" />
          <h3>8 inch coaster</h3>
          <p>Price: PKR 1100</p>
          <a class="btn" href="https://www.instagram.com/ali.art.53?igsh=dmRvNXkyYmV1cW82" target="_blank">Order on Instagram</a>
        </div>
        <div class="product">
          <img src="images/product3.jpg" alt="Product 3" />
          <h3>Key Ring</h3>
          <p>Price: PKR 300</p>
          <a class="btn" href="https://www.instagram.com/ali.art.53?igsh=dmRvNXkyYmV1cW82" target="_blank">Order on Instagram</a>
        </div>
      </div>
      <button class="prev" onclick="moveSlide(-1)">&#10094;</button>
      <button class="next" onclick="moveSlide(1)">&#10095;</button>
    </div>
  </section>

  <section id="contact" class="container">
    <h2>Contact Us</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea rows="4" placeholder="Your Message"></textarea>
      <button type="submit">Send Message</button>
    </form>
  </section>

  <footer>
    <p>&copy; 2025 Ali Art Gallery. All rights reserved.</p>
  </footer>

  <script>
    let slideIndex = 0;

    function moveSlide(n) {
      let slides = document.querySelectorAll('.product');
      slideIndex += n;

      if (slideIndex < 0) {
        slideIndex = slides.length - 1;
      }
      if (slideIndex >= slides.length) {
        slideIndex = 0;
      }

      let slider = document.querySelector('.slider');
      let width = slides[0].offsetWidth;
      slider.style.transform = `translateX(-${slideIndex * width}px)`;
    }
  </script>
</body>

</html>
