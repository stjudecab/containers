# Fusion-report Docker Image

This Dockerfile builds a container for [fusion-report](https://github.com/Clinical-Genomics/fusion-report), a tool for parsing outputs from fusion detection tools.


## Build

To build the image:

```bash
docker build -t fusion-report/3.1.1 .
```

## Usage

Run the container:

```bash
docker run --rm fusion-report:3.1.1 fusion_report [run|download|sync] [args]
```

To get help and list all possible parameters, you can use `fusion_report -h`.
For more details about how to use fusion-report, check out the original repo at [here](https://github.com/Clinical-Genomics/fusion-report).

## Features

- Compared with the official image, this customized fusion-report supports one more tool: [CTAT-LR-Fusion](https://github.com/TrinityCTAT/CTAT-LR-fusion).
- Support both the `linux/amd64` (Linux and Windows, macOS(Intel)) and `linux/arm64` (macOS(Apple Silicon)).

## License

This docker image is released under the GPLv3 License.
