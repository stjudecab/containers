# RSVRECON Docker Image

This Dockerfile builds a container for drawing trees used by the `stjudecab/rsvrecon` pipeline.


## Build

To build the image:

```bash
docker build -t rsvrecon:v4.3 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION={your_version} -t rsvrecon:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm -it rsvrecon:v4.3 R

# launch an R session and you can load the ggplot2 pacakge as follows:
> library(ggplot2)
> library(ggtree)
```

This will launch an R terminal with prompt. To use `ggplot2`, you can load the package in R with `library(ggplot2)`.
After the package is loaded, you can use the functions provided by the `ggplot2` to draw graphics and do analysis.

## Features

- Created based on `micromamba` image
- Bundled with other useful utilities (e.g. `gggenes`, `ggtree`, `treeio`, etc.)
- Support both the `linux/amd64` (Linux and Windows, macOS(Intel)) and `linux/arm64` (macOS(Apple Silicon)).

## License

This docker image is released under the MIT License.
