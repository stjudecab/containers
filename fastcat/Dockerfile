FROM mambaorg/micromamba:2-ubuntu22.04 AS source

USER $MAMBA_USER

# set work directory
WORKDIR /tmp

# copy environment file
COPY --chown=$MAMBA_USER:$MAMBA_USER environment.yml /tmp/environment.yml

# create environment from yml file
RUN micromamba env create -f environment.yml \
  && micromamba clean --all --yes \
  && rm /tmp/environment.yml

FROM mambaorg/micromamba:2-ubuntu22.04 AS final

ARG BUILD_VERSION=v0.18.6

################## METADATA ######################
LABEL base_image="micromamba:2-ubuntu22.04"
LABEL version="1"
LABEL software="fastcat"
LABEL software.version="${BUILD_VERSION}"
LABEL about.summary="Simple utility to concatenate .fastq(.gz) files whilst creating a summary of the sequences."
LABEL about.home="https://github.com/epi2me-labs/fastcat"
LABEL about.documentation="https://github.com/epi2me-labs/fastcat/blob/master/README.md"
LABEL about.license_file="https://github.com/epi2me-labs/fastcat/blob/master/LICENSE"
LABEL about.tags="Genomics"
LABEL extra.identifiers.biotools="fastcat"

COPY --from=source /opt/conda/envs/fastcat /opt/conda/envs/fastcat

RUN echo "micromamba activate fastcat" >> ~/.bashrc

WORKDIR /app

# default command
CMD ["fastcat", "--help"]

# add mantainer
MAINTAINER Haidong Yi <hyi@stjude.org>
