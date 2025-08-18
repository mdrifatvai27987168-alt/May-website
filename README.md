<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>আমার শপিং ওয়েবসাইট</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f2f2f2;
    }
    header {
      background: #f85606;
      color: white;
      padding: 15px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    header h1 { margin: 0; font-size: 22px; }
    nav a {
      color: white;
      margin: 0 10px;
      text-decoration: none;
      font-weight: bold;
    }
    .banner {
      background: url('https://i.ibb.co/tP0h0fY/daraz-banner.jpg') no-repeat center;
      background-size: cover;
      height: 200px;
    }
    .categories, .products {
      padding: 20px;
      background: white;
      margin: 10px;
      border-radius: 5px;
    }
    .categories h2, .products h2 {
      margin-bottom: 10px;
      font-size: 18px;
      color: #333;
    }
    .cat-list, .product-list {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px;
    }
    .cat-item, .product-item {
      background: #fff;
      border: 1px solid #ddd;
      border-radius: 5px;
      text-align: center;
      padding: 10px;
      transition: 0.3s;
    }
    .cat-item:hover, .product-item:hover {
      box-shadow: 0px 4px 8px rgba(0,0,0,0.1);
      transform: translateY(-3px);
    }
    .product-item img {
      width: 100%;
      height: 120px;
      object-fit: cover;
    }
    footer {
      background: #333;
      color: white;
      padding: 10px;
      text-align: center;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <header>
    <h1>আমার দোকান</h1>
    <nav>
      <a href="#">হোম</a>
      <a href="#">ক্যাটাগরি</a>
      <a href="#">অফার</a>
      <a href="#">আমার অ্যাকাউন্ট</a>
    </nav>
  </header>

  <div class="banner"></div>

  <section class="categories">
    <h2>ক্যাটাগরি</h2>
    <div class="cat-list">
      <div class="cat-item">মোবাইল</div>
      <div class="cat-item">ফ্যাশন</div>
      <div class="cat-item">ইলেকট্রনিক্স</div>
      <div class="cat-item">বিউটি প্রোডাক্ট</div>
    </div>
  </section>

  <section class="products">
    <h2>জনপ্রিয় পণ্য</h2>
    <div class="product-list">
      <div class="product-item">
        <img src="https://i.ibb.co/3Nf3WmG/phone.jpg" alt="Phone">
        <p>স্মার্টফোন - ৳12,000</p>
      </div>
      <div class="product-item">
        <img src="https://i.ibb.co/XpG4MWf/shirt.jpg" alt="Shirt">
        <p>শার্ট - ৳550</p>
      </div>
      <div class="product-item">
        <img src="https://i.ibb.co/6m9L8Hz/laptop.jpg" alt="Laptop">
        <p>ল্যাপটপ - ৳45,000</p>
      </div>
      <div class="product-item">
        <img src="https://i.ibb.co/cX7R6fD/shoes.jpg" alt="Shoes">
        <p>জুতা - ৳1200</p>
      </div>
    </div>
  </section>

  <footer>
    © 2025 আমার শপিং ওয়েবসাইট | তৈরি করেছেন আপনি নিজে 🚀
  </footer>

</body>
</html>
