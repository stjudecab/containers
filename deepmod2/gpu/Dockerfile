FROM alpine/git:2.45.2 AS source

# define build version argument
ARG BUILD_VERSION=v0.3.2

# Clone the code from github
RUN git clone https://github.com/WGLab/DeepMod2 \
   && cd DeepMod2 \
   && git checkout $BUILD_VERSION \
   && rm -rf .git

# Final stage
FROM pytorch/pytorch:2.1.2-cuda11.8-cudnn8-runtime 

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

COPY --from=source /git/DeepMod2 /workspace/DeepMod2

COPY requirements.txt /workspace/

# copy conda env file
RUN pip install --no-cache-dir -r /workspace/requirements.txt

CMD ["python", "DeepMod2/deepmod2", "--help"]

