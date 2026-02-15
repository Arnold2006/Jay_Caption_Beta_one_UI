# JoyCaption - Advanced Image Captioning Tool
![JoyCaption Screenshot](gradio-app.jpg)

# JoyCaption Beta One - Batch Processing WebUI

A powerful, user-friendly web interface for the JoyCaption image captioning model with advanced batch processing capabilities and real-time system monitoring.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.10+-green.svg)
![Gradio](https://img.shields.io/badge/gradio-5.24+-orange.svg)

## ✨ Features

### 🖼️ Image Captioning
- **Single Image Processing** - Caption individual images with real-time generation
- **Batch Processing** - Process multiple images simultaneously with progress tracking
- **Multiple Caption Types**:
  - Descriptive (Booru tag-like)
  - Descriptive (Informal)
  - Training Prompt
  - MidJourney
  - Booru tag list
  - Booru-like tag list
  - Art Critic
  - Product Listing
  - Social Media Post

### ⚡ Model Options
- **BF16 (Higher Quality)** - Full precision model (~24GB VRAM)
- **NF4 4-bit (Lower VRAM)** - Quantized model (~12-14GB VRAM)
  - Uses bitsandbytes NF4 quantization
  - Vision tower preserved in full precision for quality
  - Language model quantized for memory efficiency

### 📊 Real-Time System Monitoring
- **GPU Monitor** (Blue border)
  - GPU name and model
  - VRAM usage with visual progress bar
  - Temperature monitoring
  - GPU load percentage
  - Auto-updates every 2 seconds

- **CPU Monitor** (Red border)
  - CPU core/thread count
  - RAM usage with visual progress bar
  - CPU utilization percentage
  - Auto-updates every 2 seconds

### 🎨 User Interface
- Clean, modern Gradio interface
- Integrated progress tracking for batch operations
- Customizable caption length (any/very short/short/medium-length/long/very long)
- Extra options: subject focus, custom names, and more
- Advanced generation settings (temperature, top-p, max tokens)
- Organized accordion sections for better workflow

### 🔧 Batch Processing Features
- Drag-and-drop file upload
- Custom output folder selection
- Adjustable DataLoader workers (CPU processes)
- Configurable batch size for GPU optimization
- Real-time progress bar
- Automatic caption file generation (.txt files)
- Error handling and validation

## 📋 Requirements

### System Requirements
- **GPU**: NVIDIA GPU with CUDA support
  - Minimum 12GB VRAM (for NF4 4-bit)
  - Recommended 24GB VRAM (for BF16)
- **RAM**: 16GB minimum, 32GB recommended
- **Storage**: ~15GB for model weights
- **OS**: Windows, Linux, or macOS

### Software Requirements
- Python 3.10 or higher
- CUDA-capable GPU with drivers installed
- Pinokio (for easy installation) or manual Python environment

## 🚀 Installation

### Option 1: Pinokio (Recommended)

1. Install [Pinokio](https://pinokio.computer/)
2. Clone this repository in Pinokio:
   ```
   https://github.com/Arnold2006/Jay_Caption_Beta_one_Batch_WebUI.git
   ```
3. Run the install script
4. Launch the app

### Option 2: Manual Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Arnold2006/Jay_Caption_Beta_one_Batch_WebUI.git
   cd Jay_Caption_Beta_one_Batch_WebUI
   ```

2. Create a virtual environment:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the application:
   ```bash
   python app.py
   ```

5. Open your browser to the URL shown in the terminal (typically `http://localhost:7860`)

## 📖 Usage

### Single Image Captioning

1. Select your preferred **Model Type** (BF16 or NF4 4-bit)
2. Navigate to the **Single Image Processing** tab
3. Upload an image
4. Choose caption type and length
5. (Optional) Add extra options or edit the prompt
6. Click **Caption** to generate
7. Copy or download the generated caption

### Batch Processing

1. Select your preferred **Model Type**
2. Navigate to the **Batch Processing** tab
3. Drag and drop multiple images (PNG, JPEG, WEBP)
4. Specify the **Output Folder Path** where caption .txt files will be saved
5. Adjust **DataLoader Workers** and **Batch Size** based on your hardware
6. Click **Start Batch Process**
7. Monitor progress with the real-time progress bar
8. Caption files will be saved to your specified folder

### System Monitoring

The GPU and CPU monitors update automatically every 2 seconds, showing:
- Real-time VRAM and RAM usage
- Temperature (requires nvidia-ml-py)
- GPU and CPU load percentages
- Visual progress bars

## ⚙️ Configuration

### Generation Settings

- **Temperature**: Controls randomness (0.0 = deterministic, higher = more creative)
- **Top-p**: Nucleus sampling threshold
- **Max New Tokens**: Maximum caption length in tokens

### Performance Tuning

**For 12GB VRAM (NF4 4-bit):**
- Batch Size: 2-4
- DataLoader Workers: 2-4

**For 24GB VRAM (BF16):**
- Batch Size: 4-8
- DataLoader Workers: 4-8

**For 48GB+ VRAM (BF16):**
- Batch Size: 8-16
- DataLoader Workers: 8-16

## 🎯 Optional Enhancements

### Enhanced GPU Monitoring

For GPU temperature and utilization monitoring:
```bash
pip install nvidia-ml-py
```

## 🛠️ Troubleshooting

### Out of Memory Errors
- Switch to NF4 4-bit model
- Reduce batch size
- Reduce DataLoader workers
- Close other GPU-intensive applications

### Slow Processing
- Increase batch size (if VRAM allows)
- Increase DataLoader workers (if CPU allows)
- Ensure CUDA drivers are up to date

### Model Loading Issues
- Ensure you have sufficient disk space
- Check internet connection (first run downloads ~12GB)
- Clear Hugging Face cache if corrupted: `~/.cache/huggingface/`

## 📝 Model Information

**Base Model**: [fancyfeast/llama-joycaption-beta-one-hf-llava](https://huggingface.co/fancyfeast/llama-joycaption-beta-one-hf-llava)

**Architecture**: LLaVA (Large Language and Vision Assistant)
- Vision Tower: CLIP-based image encoder
- Language Model: LLaMA-based text generator
- Multi-modal projector connecting vision and language

**Quantization**: 
- BF16: Full bfloat16 precision
- NF4: 4-bit NormalFloat quantization via bitsandbytes
  - Only language model quantized
  - Vision components preserved in full precision

## 🙏 Credits

- **JoyCaption Model**: [fancyfeast](https://huggingface.co/fancyfeast)
- **Original WebUI Inspiration**: JoyCaption community
- **System Monitoring Design**: Inspired by Z-Fusion
- **Framework**: Gradio, Transformers, PyTorch
- **Development**: Arnold2006

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Check existing issues for solutions
- Review the troubleshooting section above

## ⭐ Acknowledgments

Special thanks to:
- The Hugging Face team for transformers and model hosting
- The Gradio team for the amazing web framework
- The bitsandbytes team for efficient quantization
- Everyone who contributed to making AI image captioning accessible

---

**Enjoy captioning your images! 🎨✨**
