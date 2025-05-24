from zipfile import ZipFile
import os

# Define file paths
base_path = "/mnt/data/scrunchies_sona"
os.makedirs(base_path, exist_ok=True)
file_path = os.path.join(base_path, "index.html")

# HTML content from the created textdoc
html_content = """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Scrunchies_Sona</title>
  <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Quicksand', sans-serif;
      background-color: #fff0f5;
      color: #333;
    }
    header {
      background-color: #e6e6fa;
      padding: 1rem 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .logo {
      font-size: 1.8rem;
      font-weight: 600;
      color: #9370DB;
    }
    nav a {
      margin: 0 1rem;
      text-decoration: none;
      color: #333;
      font-weight: 600;
    }
    .hero {
      text-align: center;
      padding: 4rem 2rem;
      background: #f8f4ff;
    }
    .hero h1 {
      font-size: 2.5rem;
      color: #9370DB;
    }
    .hero p {
      font-size: 1.2rem;
    }
    .section {
      padding: 2rem;
      max-width: 900px;
      margin: auto;
    }
    .products img, .gallery img {
      width: 150px;
      margin: 1rem;
      border-radius: 10px;
    }
    footer {
      background-color: #e6e6fa;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
    .button {
      display: inline-block;
      padding: 0.5rem 1rem;
      background-color: #9370DB;
      color: white;
      text-decoration: none;
      border-radius: 5px;
      margin-top: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">Scrunchies_Sona</div>
    <nav>
      <a href="#about">About</a>
      <a href="#products">Products</a>
      <a href="#gallery">Gallery</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section class="hero">
    <h1>Tie Up in Style</h1>
    <p>Handmade scrunchies with love and lavender vibes.</p>
    <a href="https://www.youtube.com/@Scrunchies_Sona" target="_blank" class="button">Visit Our YouTube</a>
  </section>

  <section id="about" class="section">
    <h2>About Us</h2>
    <p>Welcome to Scrunchies_Sona, your one-stop shop for beautiful, handmade scrunchies that add charm and elegance to your everyday look. Crafted with care and a splash of lavender!</p>
  </section>

  <section id="products" class="section products">
    <h2>Our Products</h2>
    <p>Explore our range of soft, stylish scrunchies designed for comfort and flair.</p>
    <div>
      <img src="https://via.placeholder.com/150?text=Scrunchie+1" alt="Scrunchie 1">
      <img src="https://via.placeholder.com/150?text=Scrunchie+2" alt="Scrunchie 2">
      <img src="https://via.placeholder.com/150?text=Scrunchie+3" alt="Scrunchie 3">
    </div>
  </section>

  <section id="gallery" class="section gallery">
    <h2>Gallery</h2>
    <p>Peek into our world of creative, cozy hair accessories.</p>
    <div>
      <img src="https://via.placeholder.com/150?text=Gallery+1" alt="Gallery 1">
      <img src="https://via.placeholder.com/150?text=Gallery+2" alt="Gallery 2">
      <img src="https://via.placeholder.com/150?text=Gallery+3" alt="Gallery 3">
    </div>
  </section>

  <section id="contact" class="section">
    <h2>Contact Us</h2>
    <p>For orders and inquiries, DM us on Instagram or visit our YouTube channel.</p>
    <p><strong>YouTube:</strong> <a href="https://www.youtube.com/@Scrunchies_Sona" target="_blank">@Scrunchies_Sona</a></p>
  </section>

  <footer>
    <p>&copy; 2025 Scrunchies_Sona. All rights reserved.</p>
  </footer>
</body>
</html>
"""

# Write HTML file
with open(file_path, "w") as f:
    f.write(html_content)

# Create ZIP file
zip_path = "/mnt/data/scrunchies_sona_website.zip"
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(file_path, arcname="index.html")

zip_path
