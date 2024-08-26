# Containers
Bioinformatics containers used in St. Jude CAB

This repository hosts a collection of **Dockerfiles** for various bioinformatics tools.
Each tool is contained in its own subdirectory, together with its specific Dockerfile and associated environment files.

## Repository Structure

```
.
├── README.md
├── tool1/
│   ├── Dockerfile
│   └── README.md
├── tool2/
│   ├── Dockerfile
│   └── README.md
├── tool3/
│   ├── Dockerfile
│   └── README.md
...
```

## Usage

Each subdirectory contains:

1. A `Dockerfile` used to build the Docker image for that specific tool.
2. A `README.md` with detailed information about:
  - Tool-specific usage instructions
  - Build arguments (if any)
  - Runtime requirements
  - Example commands
  - Tool-specific documentation links

To use a specific tool, navigate to its subdirectory and refer to the README for detailed instructions.

## Building Images

Generally, to build an image, navigate to the tool's directory and run:

```bash
docker build -t toolname:version .
```

Refer to each tool's README for specific build instructions and available build arguments.

## Contributing

If you'd like to contribute a new tool or improve an existing one, please submit a pull request.
Ensure that you include both a `Dockerfile` and a `README` for any new tools.

This repository is licensed under Apache.
Individual tools may have their own licenses. Please check each tool's `README` for specific licensing information.

## Contact

For questions or issues, please open an GitHub issue in this repository.
