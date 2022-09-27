# syntax=docker/dockerfile:1

FROM gcr.io/dataflow-templates-base/python39-template-launcher-base@sha256:778a596703e6582afa5ea291ae3d9b85baa75ecd6fec4d762a636e658666ac67


RUN apt-get update && apt-get install -y software-properties-common \
    && apt-add-repository 'deb http://security.debian.org/debian-security stretch/updates main' \
    && apt-get update \
    && apt-get -y upgrade \
    && apt-get install -y openjdk-8-jre libffi-dev git proj-bin \
    && rm -rf /var/lib/apt/lists/* \
    # Upgrade pip and install the requirements.
    && pip install --no-cache-dir --upgrade pip \
    # https://stackoverflow.com/questions/64813705/dataflow-with-python-flex-template-launcher-timeout
    && pip install -U apache-beam[gcp]==2.41.0 
