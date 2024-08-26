Here's the README for the GPU version of the DeepMod2 Dockerfile:

# DeepMod2 Docker Image (GPU Version)

This Dockerfile builds a GPU-enabled container for DeepMod2, a tool for DNA 5mC methylation detection from Oxford Nanopore reads.

## Build

To build the image:

```bash
docker build -t deepmod2-gpu:v0.3.2 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION=v0.3.2 -t deepmod2-gpu:v0.3.2 .
```

Alternatively, you can use the first 7 characters of a GitHub commit SHA:

```bash
docker build --build-arg BUILD_VERSION=a1f428d -t deepmod2-gpu:a1f428d .
```

## Usage

Run the container with GPU support:

```bash
docker run --gpus all --rm deepmod2-gpu:v0.3.2 python DeepMod2/deepmod2 --help
```

This will display the help message for DeepMod2. To run specific commands, replace `--help` with your desired arguments.

## Features

- Based on PyTorch 2.1.2 with CUDA 11.8 and cuDNN 8
- GPU-accelerated for faster processing
- DeepMod2 version: v0.3.2 (default, can be changed during build)

## Requirements

- Docker with NVIDIA GPU support
- NVIDIA drivers compatible with CUDA 11.8

## License

DeepMod2 is released under the MIT License.

For more information, visit: https://github.com/WGLab/DeepMod2
