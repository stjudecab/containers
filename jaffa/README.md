# JAFFA Docker Image

This Dockerfile builds a container for [JAFFA](https://github.com/Oshlack/JAFFA), a multi-step pipeline that takes either raw RNA-Seq reads, or pre-assembled transcripts, then searches for gene fusions.


## Build

To build the image:

```bash
docker build -t jaffa:2.3 .
```

## Usage

To run the container, please refer to the documentation at [here](https://github.com/Oshlack/JAFFA/wiki/HowToSetUpJAFFA). Jaffa pipeline uses [bpipe](https://github.com/ssadedin/bpipe) to manage and launch the pipeline.

## Features

- Modified the official image by adding `procpc` package, so that the `ps` command can be used in the container.
- After this modification, this container can work in `Nextflow`-based pipelines.
- Reason for generating this image: Fix the issue at https://github.com/nf-core/nanoseq/issues/239.

## License

This docker image is released under the GPL License. The original license can be found at [here](https://github.com/Oshlack/JAFFA/blob/master/LICENSE).
