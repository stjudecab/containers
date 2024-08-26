# DeepMod2 Docker Image

This Dockerfile builds a container for DeepMod2, a tool for DNA 5mC methylation detection from Oxford Nanopore reads.

## Build

To build the image:

```bash
docker build -t deepmod2:v0.3.2 .
```

You can specify a different version using the BUILD_VERSION argument:

```bash
docker build --build-arg BUILD_VERSION=v0.3.3 -t deepmod2:v0.3.3 .
```

Alternatively, you can use the first 7 characters of a GitHub commit SHA:

```bash
docker build --build-arg BUILD_VERSION=1234567 -t deepmod2:1234567 .
```

## Usage

Run the container:

docker run --rm deepmod2:v0.3.2 python DeepMod2/deepmod2 --help

This will display the help message for DeepMod2. To run specific commands, replace --help with your desired arguments.

## Features

- Based on Python 3.9.19 slim Bullseye
- Includes PyTorch 2.1.2 (CPU version)
- DeepMod2 version: v0.3.2 (default, can be changed during build)

## License

DeepMod2 is released under the MIT License.

For more information, visit: https://github.com/WGLab/DeepMod2
