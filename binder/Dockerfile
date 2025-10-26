FROM jupyter/base-notebook:latest

USER root

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      build-essential \
      gfortran \
      cmake \
      liblapack-dev \
      libblas-dev \
      make \
      git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER jovyan

COPY binder/requirements.txt /tmp/
RUN pip install --no-cache-dir -r /tmp/requirements.txt

WORKDIR /home/jovyan
