# Pandas Docker Image

This Dockerfile builds a container for Pandas, a flexible and powerful data analysis / manipulation library for Python


## Build

To build the image:

```bash
docker build -t pandas:2.1.2 .
```

You can specify a different version using the `BUILD_VERSION` argument:
Note: the `BUILD_VERSION` should be in `x.x.x` format and can be found in the available versions of `pandas` library.

```bash
docker build --build-arg BUILD_VERSION={your_version} -t pandas:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm pandas:2.1.2 python --help
```

## License

BSD 3-Clause License
