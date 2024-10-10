FROM quay.io/biocontainers/perl:5.26.2

# set software version
ARG BUILD_VERSION=v20.06

################## METADATA ######################
LABEL base_image="quay.io/biocontainers/perl:5.26.2"
LABEL version="1"
LABEL software="Annovar"
LABEL software.version="${BUILD_VERSION}"
LABEL about.summary="ANNOVAR is an efficient software tool to utilize update-to-date information to functionally annotate genetic variants detected from diverse genomes"
LABEL about.home="https://annovar.openbioinformatics.org/en/latest/"
LABEL about.documentation="https://annovar.openbioinformatics.org/en/latest/#annovar-documentation"
LABEL about.tags="Bioinformatics"
LABEL extra.identifiers.biotools="Annovar"

# set the working diectory
WORKDIR /annovar
COPY ./src/*.pl /annovar

# export annovar to the path
ENV PATH /annovar:$PATH

CMD [ "table_annovar.pl", "-h" ]

