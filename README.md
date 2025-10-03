# MLX, PyTorch & Hugging Face Demo on MacBook Pro (M4 Pro+)

## Introduction

This project demonstrates how to leverage Apple's powerful M4 Pro chip for machine learning workloads using three complementary frameworks:

- **MLX**: Apple's native machine learning framework optimized for Apple Silicon
- **PyTorch with MPS**: The popular deep learning framework with Metal Performance Shaders support
- **Hugging Face**: Access to state-of-the-art pre-trained models and transformers

## Why This Combination?

The MacBook M4 Pro offers exceptional performance for machine learning tasks when properly configured:

### 🚀 **Apple MLX Framework**
- Native optimization for Apple Silicon architecture
- Unified memory access for efficient model training and inference
- Seamless integration with Metal Performance Shaders
- Optimized for transformer models and large language models

### ⚡ **PyTorch with MPS Backend**
- Industry-standard deep learning framework
- Metal Performance Shaders (MPS) acceleration on Apple Silicon
- Broad ecosystem support and extensive documentation
- Easy migration from CUDA-based workflows

### 🤗 **Hugging Face Integration**
- Access to thousands of pre-trained models
- Streamlined model downloading and management
- Compatible with both MLX and PyTorch backends
- Community-driven model repository

## Hardware Advantages of M4 Pro

The MacBook M4 Pro provides several advantages for ML workloads:

- **Unified Memory Architecture**: Shared memory between CPU and GPU eliminates data transfer bottlenecks
- **High Memory Bandwidth**: Up to 273 GB/s memory bandwidth for large model handling
- **Neural Engine**: Dedicated 16-core Neural Engine for optimized ML operations
- **Energy Efficiency**: Superior performance-per-watt compared to traditional GPU setups

## Prerequisites

- MacBook with M4 Pro chip (or other Apple Silicon)
- macOS 14.0 or later
- Python 3.9+
- UV package manager (recommended) or pip

## Installation

### 1. Install Required Packages

```bash
# Install MLX, transfer learning utilities, and tokenization support
$ uv add mlx tf-transfer sentencepiece

# Install Hugging Face CLI tools
$ uv tool install "huggingface-hub[cli]"

# Install PyTorch with MPS support (if not already installed)
$ uv add torch torchvision torchaudio
```

### 2. Download Pre-trained Models

```bash
# Download Mistral 7B model optimized for MLX
$ uvx -w "hf-transfer" --from "huggingface-hub[cli]" huggingface-cli download \
  --local-dir-use-symlinks False \
  --local-dir mistral-7B-v0.1 \
  mlx-model/mistral-7B-v0.1
```

## Features Demonstrated

This project showcases:

- ✅ **Device Detection**: Automatic detection and utilization of Apple Silicon GPU via MPS
- ✅ **MLX Integration**: Native Apple Silicon optimization for ML workloads  
- ✅ **Model Loading**: Efficient loading of Hugging Face models
- ✅ **Performance Comparison**: Benchmarking between CPU, MPS, and MLX backends
- ✅ **Memory Management**: Optimal memory usage with unified memory architecture

## Project Structure

```
torch-mps-demo/
├── main.py              # Main demonstration script
├── README.md            # This file
├── mistral-7B-v0.1/     # Downloaded model files (created after setup)
└── requirements.txt     # Python dependencies (if using pip)
```

## Usage

Run the main demonstration:

```bash
python main.py
```

This will automatically detect your hardware capabilities and run appropriate tests for:
- PyTorch MPS backend functionality
- MLX framework integration
- Hugging Face model loading and inference

## Performance Tips

1. **Memory Management**: Close unnecessary applications to maximize available unified memory
2. **Thermal Management**: Ensure proper ventilation for sustained performance
3. **Model Sizing**: Choose model sizes appropriate for your M4 Pro's memory configuration
4. **Batch Processing**: Optimize batch sizes for your specific hardware configuration
