FROM hbpmip/python-mip:0.2.4

MAINTAINER jan.kralj@ijs.si

ENV DOCKER_IMAGE=hbpmip/python-hinmine:0.1.0 \
    FUNCTION=python-hinmine

# Install system packages
RUN apt-get update
RUN apt-get install -y git gcc python3-dev

# Update pip
RUN python -m pip install --upgrade pip
# Install hinmine and its requirements
RUN git clone -b python3 https://github.com/JanKralj/cf_netSDM.git

WORKDIR cf_netSDM
RUN python setup.py install
WORKDIR /

RUN pip install -r cf_netSDM/requirements.txt
RUN pip install -r requirements.txt

RUN rm -rf cf_netSDM

COPY mip_hinmine.py /mip_hinmine.py

ENTRYPOINT ["python", "mip_hinmine.py"]

LABEL org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="hbpmip/python-hinmine" \
      org.label-schema.description="HINMine algorithm for network propositionalization" \
      org.label-schema.url="https://github.com/LREN-CHUV/algorithm-repository" \
      org.label-schema.vcs-type="git" \
      org.label-schema.vcs-url="https://github.com/LREN-CHUV/algorithm-repository.git" \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.version="$VERSION" \
      org.label-schema.vendor="LREN CHUV" \
      org.label-schema.license="AGPLv3" \
      org.label-schema.docker.dockerfile="Dockerfile" \
      org.label-schema.schema-version="1.0"
