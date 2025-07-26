


# 🎨 Image Color Extractor

A simple Python script to extract and visualize dominant colors from an image using KMeans clustering.

---

## 📌 Features

- Extracts **dominant RGB colors** from any image
- Displays RGB values in a readable format
- Creates and shows a **color palette image**
- Optionally saves the palette to a file (`color_palette.png`)

---

## 🖼️ Example Output

For a given image, the script might output:

```

Pattern 1 : RGB -> RED: 234  GREEN: 195  BLUE: 123
Pattern 2 : RGB -> RED: 45   GREEN: 67   BLUE: 89
...

````

And display a color palette image with horizontal color strips.

---

## 🛠️ Requirements

- Python 3.7+
- Libraries:
  - `numpy`
  - `pillow`
  - `scikit-learn`
  - `matplotlib` (optional, for color plotting)

Install them using pip:

```bash
pip install numpy pillow scikit-learn matplotlib
````

---

## 🚀 How to Use

1. Clone this repository:

   ```bash
   git clone https://github.com/ikram-3/dominant-color-detector.git
   cd dominant-color-detector
   ```

2. Place your input image in the project folder and update the image path in the script:

   ```python
   image_path = 'your_image.png'
   ```

3. Run the script:

   ```bash
   python extract_colors.py
   ```

4. The extracted colors will be printed, and a palette image will be shown and saved as `color_palette.png`.

---

## 🧠 How It Works

The script uses **KMeans clustering** to group all pixels into `n` color clusters.
Each cluster center represents one dominant color from the image.

---

## 📁 Project Structure

```
image-color-extractor/
│
├── extract_colors.py         # Main script
├── color_palette.png         # Output (auto-generated)
├── your_image.png            # Input image (replace this)
└── README.md                 # Project description
```

---

## 📃 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Muhammad Ikram**
Swat, Pakistan
Self-taught learner passionate about Data Science and Python.



