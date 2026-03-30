# AudioCraft Docker with CUDA Support

This project provides Dockerfiles for running Meta's AudioCraft (MusicGen) with different CUDA versions (12.9, 12.8, 12.4, and 12.1). This repository was developed through collaboration with Claude 3.5 Sonnet (Anthropic) to extend the original CUDA 11.8 implementation, which was independently created by the repository owner.

## 📺 Resources & Documentation

- [Tutorial Blog Post](https://minokamo.tokyo/2023/10/08/6321/)
- [Tutorial Blog Post English](https://betelgeuse.work/audiocraft-docker/)
- [Video Guide on YouTube](https://youtu.be/r13qBmuFtRM)

## 🌟 Features

- Support for latest CUDA versions (13.2, 12.9, 12.8, 12.4, 12.1)
- Optimized dependency management
- Ready-to-use Docker configurations
- Gradio web interface for easy interaction
- Detailed documentation and testing guidelines

## 🚀 Quick Start

```bash
# Build the Docker image (Choose your CUDA version)
docker build -f Dockerfile.cuda129 -t audiocraft:cuda129 .

# Run the container
docker run --gpus all -p 7860:7860 audiocraft:cuda129
```

Then open your browser and navigate to `http://localhost:7860`

## 📦 Supported Versions

### CUDA 13.2 (Experimental - Untested)
- **WARNING: This Dockerfile has NOT been build-tested. It may fail due to dependency conflicts (xformers, torchtext, gradio compatibility with PyTorch nightly).**
- Uses PyTorch nightly builds for CUDA 13.2
- Optimized for newest NVIDIA GPUs
- Contributions and test reports welcome
- [Dockerfile.cuda132](./Dockerfile.cuda132)

### CUDA 12.9
- Latest CUDA support
- Uses PyTorch 2.9.0 nightly builds (development version)
- Optimized for newest NVIDIA GPUs
- [Dockerfile.cuda129](./Dockerfile.cuda129)

### CUDA 12.8
- Latest stable CUDA support
- Uses PyTorch 2.7.0 stable
- Recommended for production use
- [Dockerfile.cuda128](./Dockerfile.cuda128)

### CUDA 12.4
- Latest CUDA support
- Uses PyTorch 2.4.0
- Optimized for newer NVIDIA GPUs
- [Dockerfile.cuda124](./Dockerfile.cuda124)

### CUDA 12.1
- Stable version
- Widely tested
- [Dockerfile.cuda121](./Dockerfile.cuda121)

## 🛠️ Requirements

- Docker
- NVIDIA GPU with appropriate CUDA support
- nvidia-docker2
- At least 8GB GPU memory recommended

## 🎵 Usage Examples

Test your installation with these prompts:

```text
"A gentle piano melody with soft strings in the background, calm and peaceful"
"Electronic dance music with a strong beat, synthesizer leads"
"Jazz quartet with acoustic bass, piano, drums, and saxophone"
```

Configuration options:
- Duration: Up to 120 seconds (maximum length)
- Temperature: 0.6-1.0 (recommended)
- Guidance scale: 3.0 (default)

Note: While longer generations (up to 120 seconds) are possible, they require more GPU memory and processing time. For testing, starting with shorter durations (30-60 seconds) is recommended.

## 🤖 Development Credits

This project represents a collaborative effort:

- Initial CUDA 11.8 implementation: Repository owner
- CUDA 12.1 & 12.4 implementations: Developed in collaboration with Claude 3.5 Sonnet
- Video tutorials and documentation: Repository owner

The AI collaboration provided:
- Dockerfile optimization
- Dependency resolution strategies
- Testing methodologies
- Documentation structure

## 🔍 Technical Details

The project addresses several technical challenges:
- CUDA version compatibility management
- PyTorch dependency resolution
- Binary compatibility across versions
- Optimal container configuration

### Implementation Notes
- CUDA 12.4 support includes some 12.1 binaries due to backward compatibility
- Careful consideration of dependency versions for stability
- Optimized for both performance and reliability

## 📚 Dependencies

Core components:
- Python 3.9
- PyTorch (version varies by CUDA)
- AudioCraft (Meta's MusicGen)
- Various audio processing libraries

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ✨ Acknowledgments

- [Meta's AudioCraft Team](https://github.com/facebookresearch/audiocraft)
- Claude 3.5 Sonnet (Anthropic) for development assistance
- The open-source community

## 📞 Support

If you encounter any issues or have questions:
1. Check the [Issues](../../issues) section
2. Create a new issue with detailed information
3. Reference the blog post or YouTube video for additional context
4. Join our discussions