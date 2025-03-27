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

ARG BUILD_VERSION=2.17.3

################## METADATA ######################
LABEL base_image="micromamba:2-ubuntu22.04"
LABEL version="1"
LABEL software="igv-tools"
LABEL software.version="${BUILD_VERSION}"
LABEL about.summary="Command line tools for IGV"
LABEL about.tags="Genomics"
LABEL about.license="MIT"

COPY --from=source /opt/conda/envs/igvtools /opt/conda/envs/igvtools

# Won't be activated unless you we login via /bin/bash command
# RUN echo "micromamba activate fastcat" >> ~/.bashrc 

# set fastcat as the default environment
# !!! this step is important or you cannot packages installed in this environment
ENV ENV_NAME igvtools
ENV PATH=/opt/conda/envs/igvtools/bin:$PATH

WORKDIR /app

# default command
CMD ["igvtools", "help"]

# add mantainer
MAINTAINER Haidong Yi <hyi@stjude.org>
