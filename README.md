# JoyCaption - Advanced Image Captioning Tool
![JoyCaption Screenshot](gradio-app.webp)

This is a simple Gradio GUI for the JoyCaption model with enhanced usability and stability.

## Installation

### Prerequisites
- Python 3.8+ 
- CUDA-capable GPU (recommended)
- At least 24GB VRAM recommended

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/joy-caption.git
   cd joy-caption/gradio-app
   ```

2. Set up a Python virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the application:
   ```bash
   python app.py
   ```

5. Open your web browser and navigate to the URL displayed in the terminal (typically http://127.0.0.1:7860)

### Optional: Install Liger Kernel
For faster inference, you can install the Liger Kernel: https://github.com/linkedin/Liger-Kernel

## Usage

### Single Image Captioning
1. Upload an image using the left-hand panel
2. Select a caption type and desired caption length
3. (Optional) Open "Extra Options" and select any additional parameters
4. (Optional) Adjust generation settings like temperature and top-p values
5. Click "Caption" to generate
6. The generated caption will appear in the output box and can be copied or edited

### Batch Processing
1. Switch to the "Batch Processing" tab
2. Upload multiple images (PNG/JPEG/WEBP)
3. Specify an output folder path where caption .txt files will be saved (the folder must already exist)
4. Set the DataLoader Workers (CPU processes) and Batch Size based on your system capabilities
5. Click "Start Batch Process"
6. Caption files will be saved as .txt files in your specified output folder (one .txt file per image with matching filenames)

## Caption Types

| Mode | Description |
|------|-------------|
| **Descriptive** | Formal, detailed prose description |
| **Descriptive (Casual)** | Similar to Descriptive but with a friendlier, conversational tone |
| **Straightforward** | Objective, no fluff, and more succinct than Descriptive |
| **Stable Diffusion Prompt** | Reverse-engineers a prompt for Stable Diffusion models |
| **MidJourney** | Similar to the above but tuned for MidJourney's prompt style |
| **Danbooru tag list** | Comma-separated tags following Danbooru conventions |
| **e621 tag list** | Alphabetical, namespaced tags in e621 style |
| **Rule34 tag list** | Rule34 style alphabetical tag dump |
| **Booru-like tag list** | Looser tag list for general labeling |
| **Art Critic** | Art-historical commentary on composition, symbolism, style, etc. |
| **Product Listing** | Marketing copy as if selling the depicted object |
| **Social Media Post** | Catchy caption for social media platforms |

> **Note on Booru modes**: They're optimized for anime-style/illustration imagery; accuracy may decrease with real-world photographs or abstract artwork.

## Features

- **BFloat16 precision** for optimal quality and performance
- **Batch processing** with customizable output locations
- **Flexible caption styles** from formal descriptions to social media posts
- **Adjustable generation parameters** (temperature, top-p, max tokens)
- **Clean, accessible UI** with improved visibility and layout
- **Progress tracking** for batch operations
