# Fastcat Docker Image

This Dockerfile builds a container for Fastcat, a tool that provides simple utilities to concatenate .fastq(.gz) files whilst creating a summary of the sequences.


## Build

To build the image:

```bash
docker build -t fastcat:v0.18.6 .
```

You can specify a different version using the `BUILD_VERSION` argument:

```bash
docker build --build-arg BUILD_VERSION={your_version} -t fastcat:{your_version} .
```

## Usage

Run the container:

```bash
docker run --rm fastcat:v0.18.6 fastcat --help
```

This will display the help message for `Fastcat`. To run specific commands, replace `--help` with your desired arguments.

## Features

- Created based on `micromamba` image
- Bundled with other useful utilities (e.g. `bzip2`, `split`, etc.)
- Fastcat version: v0.18.6 (default, can be changed during build). For more versions, you can check it using `conda / mamba search`.

## License

Copyright (c) 2020-, Oxford Nanopore Technologies Plc. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* All advertising materials mentioning features or use of this software must
  display the following acknowledgement: This product includes software
  developed by Oxford Nanopore Technologies Plc.

* Neither the name of Oxford Nanopore Technologies Plc. nor the names of
  its contributors may be used to endorse or promote products derived from this
  software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY Oxford Nanopore Technologies Plc. AS IS AND ANY
EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL Oxford Nanopore Technologies Plc. BE LIABLE FOR ANY DIRECT,
INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE
OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

