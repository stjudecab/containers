# first stage
FROM alpine/git:2.45.2 AS source

# define build version argument
ARG BUILD_VERSION=v0.3.2

# set workdir
WORKDIR /app

# Clone the code from github
RUN git clone https://github.com/WGLab/DeepMod2 \
   && cd DeepMod2 \
   && git checkout $BUILD_VERSION \
   && rm -rf .git

# Second stage
FROM pytorch/pytorch:2.1.2-cuda11.8-cudnn8-runtime 

ARG BUILD_VERSION=v0.3.2

################## METADATA ######################
LABEL base_image="pytorch/pytorch:2.1.2-cuda11.8-cudnn8-runtime"
LABEL version="1"
LABEL software="DeepMod2"
LABEL software.version="${BUILD_VERSION}"
LABEL about.summary="DNA 5mC methylation detection from Dorado or Guppy basecalled Oxford Nanopore reads"
LABEL about.home="https://github.com/WGLab/DeepMod2"
LABEL about.documentation="https://github.com/WGLab/DeepMod2/blob/main/README.md"
LABEL about.license_file="https://github.com/WGLab/DeepMod2/blob/main/LICENSE"
LABEL about.license="MIT License"
LABEL about.tags="Genomics"
LABEL extra.identifiers.biotools="DeepMod2"

# set work directory
WORKDIR /workspace

# copy codes from 1st stage
COPY --from=source /app/ /workspace/

# copy other utility dependencies
COPY requirements.txt /workspace/

# install the utilities
RUN pip install --no-cache-dir -r /workspace/requirements.txt \
  && rm /workspace/requirements.txt

CMD ["python", "DeepMod2/deepmod2", "--help"]

MAINTAINER Haidong Yi <hyi@stjude.org>
