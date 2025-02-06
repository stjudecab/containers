FROM davidsongroup/jaffa:2.4

# define build version argument
ARG BUILD_VERSION=2.3

# install ps command for nextflow
RUN apt-get update && apt-get install -y procps

# link reformat.sh to reformat
RUN ln -s /JAFFA/tools/bin/reformat /JAFFA/tools/bin/reformat.sh

# clear the entrypoint
ENTRYPOINT []

CMD ["/JAFFA/tools/bin/bpipe", "run"]

# add mantainer
MAINTAINER Haidong Yi <hyi@stjude.org>
