# first stage
FROM alpine/git:2.45.2 AS source

# set workdir
WORKDIR /app

# Clone the codes from github
RUN git clone https://github.com/stjudecab/fusion-report \
   && cd fusion-report \
   && rm -rf .git docs tests

# Second stage
FROM python:3.9.19-slim-bullseye AS final

# define build version argument
ARG BUILD_VERSION=3.1.1

# install procps
RUN apt-get update && apt-get install -y procps sqlite3

################## METADATA ######################
LABEL base_image="python:3.9.19-slim-bullseye"
LABEL version="1"
LABEL software="fusion-report"
LABEL software.version="${BUILD_VERSION}"
LABEL about.summary="Tool for parsing outputs from fusion detection tools"
LABEL about.home="https://github.com/Clinical-Genomics/fusion-report"
LABEL about.documentation="https://matq007.github.io/fusion-report/example/"
LABEL about.license_file="https://github.com/Clinical-Genomics/fusion-report/blob/master/LICENSE"
LABEL about.license="GPLv3"
LABEL about.tags="Bioinformatics"

# set work directory
WORKDIR /workspace

# copy codes from 1st stage
COPY --from=source /app/ /workspace

# Install dependecies (e.g. numpy and pandas)
RUN cd /workspace/fusion-report && \
    pip install --no-cache-dir -r ./requirements.txt && \
    python setup.py install 

CMD ["fusion_report", "-h"]

# add mantainer
MAINTAINER Haidong Yi <hyi@stjude.org>
