# AI-Powered Texture Manipulation Tool

## Overview
This project is a Python-based application that allows users to:
- **Select objects with hand-assisted input** (drawn area for selection).
- **Generate textures and effects based on a text prompt**.
- **Apply and blend textures** to the selected area while preserving the original details.

The goal is to provide an efficient way to manipulate textures and materials on images while maintaining real texture details. Example use case: A user selects a skin area in an image and prompts the AI to generate a **yellow sponge texture**, which is then blended with the real skin.

## Features
✅ Hand-assisted selection using brush/polygon-based tools.
✅ AI-powered texture generation from text prompts (Stable Diffusion, Kandinsky, DALL-E, etc.).
✅ Multiple blending modes (Overlay, Multiply, Soft Light, etc.).
✅ User-friendly interface for importing/exporting images.
✅ Undo/Redo support.

## Use Cases
🎨 **Artistic Editing** – Apply creative textures to objects.
👕 **Fashion & Material Design** – Experiment with different fabric patterns.
🔍 **Forensic & Reconstruction Work** – Restore missing details in images.

## Tech Stack
- **Python** – Core programming language.
- **OpenCV** – Image processing and object selection.
- **PyQt/Tkinter** – GUI for user interaction.
- **Stable Diffusion / DALL-E** – AI texture generation.
- **NumPy/PIL** – Additional image manipulation.

## Installation
### Prerequisites
- Python 3.8+
- Pip & Virtual Environment
- Dependencies listed in `requirements.txt`

### Setup
```bash
# Clone the repository
git clone https://github.com/your-username/ai-texture-tool.git
cd ai-texture-tool

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Usage
```bash
python main.py
```
1. Load an image.
2. Select the area to modify.
3. Enter a texture description (e.g., *"metallic scales"*).
4. Apply and adjust blending.
5. Export the final image.

