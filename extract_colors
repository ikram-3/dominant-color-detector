import numpy as np
from PIL import Image
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

def extract_colors(image_path, n_colors):
    """
    Extract dominant colors from an image using KMeans clustering.

    Parameters:
        image_path (str): Path to the input image.
        n_colors (int): Number of colors to extract.

    Returns:
        np.ndarray: Array of dominant colors in RGB.
    """
    # Load and convert image to RGB
    img = Image.open(image_path)
    img = img.convert("RGB")
    
    # Convert to NumPy array and reshape
    img_np = np.array(img)
    pixels = img_np.reshape((-1, 3))

    # Apply KMeans clustering
    kmeans = KMeans(n_clusters=n_colors, random_state=42)
    kmeans.fit(pixels)
    
    # Get cluster centers (dominant colors)
    dominant_colors = kmeans.cluster_centers_.astype(int)

    return dominant_colors

def display_colors(colors):
    """
    Print the extracted colors in RGB format.

    Parameters:
        colors (np.ndarray): Array of colors.
    """
    for i, color in enumerate(colors):
        print(f'Pattern {i+1} : RGB -> RED: {color[0]}  GREEN: {color[1]}  BLUE: {color[2]}')

def create_palette_image(colors, height=60, width_per_color=100, save_path=None):
    """
    Create and optionally save a color palette image from extracted colors.

    Parameters:
        colors (np.ndarray): Array of colors.
        height (int): Height of the palette image.
        width_per_color (int): Width for each color block.
        save_path (str): Path to save the image. If None, the image is not saved.

    Returns:
        PIL.Image: The created color palette image.
    """
    n_colors = colors.shape[0]
    palette_width = width_per_color * n_colors

    # Create empty image array
    image_array = np.zeros((height, palette_width, 3), dtype=np.uint8)

    # Fill in each color
    for i, color in enumerate(colors):
        image_array[:, i*width_per_color:(i+1)*width_per_color] = color

    # Convert to image
    img = Image.fromarray(image_array, mode='RGB')

    # Show and optionally save
    img.show()
    if save_path:
        img.save(save_path)
        print(f'Color palette saved to: {save_path}')
    
    return img

# =====================
# === MAIN EXECUTION ==
# =====================
if __name__ == '__main__':
    # Input image and number of colors to extract
    image_path = '../image.png'  # Change this path as needed
    n_colors = 5

    # Extract, display, and create palette
    colors = extract_colors(image_path, n_colors)
    display_colors(colors)
    create_palette_image(colors, save_path='color_palette.png')
