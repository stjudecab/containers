FROM python:3.9.19-slim-bullseye AS final

# define build version argument
ARG BUILD_VERSION=2.1.2

# set workdir
WORKDIR /app

# install procps
RUN apt-get update && apt-get install -y procps

################## METADATA ######################
LABEL base_image="python:3.9.19-slim-bullseye"
LABEL version="1"
LABEL software="pandas"
LABEL software.version="${BUILD_VERSION}"
LABEL about.summary="Flexible and powerful data analysis / manipulation library for Python"
LABEL about.home="https://github.com/pandas-dev/pandas"
LABEL about.documentation="https://pandas.pydata.org/docs/"
LABEL about.license_file="https://github.com/pandas-dev/pandas/blob/main/LICENSE"
LABEL about.license="BSD-3"
LABEL about.tags="Data Science"

# Install dependecies (e.g. pandas)
RUN pip install --no-cache-dir pandas==${BUILD_VERSION}

CMD ["python", "--help"]

MAINTAINER Haidong Yi <hyi@stjude.org>
