# RSVRECON REPORT Docker Image

This Dockerfile builds a container for generating reports used by the `stjudecab/rsvrecon` pipeline.

## Build

To build the image:

```bash
docker build -t rsvrecon_report:v0.1 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION={your_version} -t rsvrecon_report:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm -it rsvrecon_report:v0.1 python

# launch a python session and you can load the reportlab package as follows:
> import reportlab
```

This will launch a python terminal with prompt. To use `reportlab`, you can load the package in python with `import reportlab`.
After the package is loaded, you can use the functions provided by the `reportlab` to generate report.

## Features

- Created based on `micromamba` image
- Bundled with other useful utilities (e.g. `pandas`, `reportlab`, `seaborn`, etc.)
- Support both the `linux/amd64` (Linux and Windows, macOS(Intel)) and `linux/arm64` (macOS(Apple Silicon)).

## License

This docker image is released under the MIT License.
