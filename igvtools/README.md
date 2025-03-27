# IgvTools Docker Image

This Dockerfile builds a docker image (`igvtools`) of command line tools for [IGV](http://www.broadinstitute.org/igv/).


These python packages provide a command line tool to interact with the powerful Integrative Genomics Viewer (IGV) for the visual exploration of genomic data.

## Build

To build the image:

```bash
docker build -t igvtools:2.17.3 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION={your_version} -t igvtools:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm igvtools:2.17.3 igvtools help
```

This will display the help message for `igvtools`. To run specific commands, replace `igvtools help` with your desired sub-commands such as `count` and `sort`.

## Features

- `igvtools count`: computes average feature density over a specified window size across the genome.
- `igvtools sort`:  sorts the input file by start position.
- `igv version`: show the version of igvtools.

## License

This docker image is released under the MIT License.
