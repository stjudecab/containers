# Annovar Docker Image

This Dockerfile builds a container for Annovar, a tool for utilizing update-to-date information to functionally annotate genetic variants detected from diverse genomes

## Build

To build the image:

```bash
docker build -t deepmod2:v20.06 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION={your_version} -t deepmod2:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm annovar:v20.06 table_annovar.pl -h
```

This will display the help message for `Annovar`. To run specific commands, replace `--help` with your desired arguments.

## Features

- Based on perl 5.26.2 image
- Annovar version: v20.06 (default, can be changed during build)

## License

ANNOVAR is freely available to personal, academic and non-profit use only. You cannot redistribute ANNOVAR to other users including lab members. No liability for software usage is assumed.

If you are a commercial user/service provider, you are required to purchase a license to ANNOVAR from [QIAGEN](https://digitalinsights.qiagen.com/). For more information on how to obtain a commercial license please [click here](https://digitalinsights.qiagen.com/products-overview/clinical-insights-portfolio/annovar/).

