# syntax=docker/dockerfile:1

FROM gcr.io/dataflow-templates-base/python3-template-launcher-base:20220418_RC00


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
