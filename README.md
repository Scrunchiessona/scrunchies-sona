from zipfile import ZipFile
import os
import shutil

# Recreate directory structure after code environment reset
base_path = "/mnt/data/scrunchies_sona"
images_path = os.path.join(base_path, "images")
os.makedirs(images_path, exist_ok=True)

# Copy uploaded image files to the images directory
uploaded_files = {
    "sc imgg.jpeg": "/mnt/data/sc imgg.jpeg",
    "sc ikmgg.avif": "/mnt/data/sc ikmgg.avif",
    "sc ikmgg.webp": "/mnt/data/sc ikmgg.webp",
    "sc ikmhg.webp": "/mnt/data/sc ikmhg.webp",
    "sc img.webp": "/mnt/data/sc img.webp"
}

for filename, src_path in uploaded_files.items():
    shutil.copy(src_path, os.path.join(images_path, filename))

# Create a simple HTML file referring to these images (recreating index.html)
index_html_content = """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Scrunchies_Sona</title>
</head>
<body>
  <h1>Scrunchies Gallery</h1>
  <div>
    <img src="images/sc imgg.jpeg" width="200">
    <img src="images/sc ikmgg.avif" width="200">
    <img src="images/sc ikmgg.webp" width="200">
    <img src="images/sc ikmhg.webp" width="200">
    <img src="images/sc img.webp" width="200">
  </div>
</body>
</html>
"""

# Save the HTML file
index_path = os.path.join(base_path, "index.html")
with open(index_path, "w") as f:
    f.write(index_html_content)

# Create a ZIP file including the HTML and image files
zip_path = "/mnt/data/scrunchies_sona_website_with_images.zip"
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(index_path, arcname="index.html")
    for filename in uploaded_files:
        zipf.write(os.path.join(images_path, filename), arcname=f"images/{filename}")

zip_path

