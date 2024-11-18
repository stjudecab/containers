# Scpy Docker Image

This Dockerfile builds a docker image (`scpy`) for python's data science utilities in single-cell data analysis. In this image, we bundled a few python packages:

- numpy
- pandas
- scipy
- polars
- editdistance
- umi_tools

These python packages are useful in many applications of single-cell omics data analysis, especially for processing mapping and tagging results.

## Build

To build the image:

```bash
docker build -t scpy:v0.1 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION={your_version} -t scpy:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm scpy:v0.1 python --help
```

This will display the help message for `Python`. To run specific commands, replace `python --help` with your desired commands that run python scripts.

## Features

- Created based on `micromamba` image
- Bundled with useful python packages (e.g. `numpy`, `panads` and `polars` etc.)
- For single-cell data analysis, we also added the python packages: `editdistance` and `umi_tools`.

## License

This docker image is released under the MIT License.
