FROM davidsongroup/jaffa:2.4

# define build version argument
ARG BUILD_VERSION=2.3

# install ps command for nextflow
RUN apt-get update && apt-get install -y procps

# clear the entrypoint
ENTRYPOINT []

CMD ["/JAFFA/tools/bin/bpipe", "run"]

# add mantainer
MAINTAINER Haidong Yi <hyi@stjude.org>
