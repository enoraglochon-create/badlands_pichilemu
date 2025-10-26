FROM jupyter/base-notebook:latest

USER root

# ⚙️ Instala make (y build-essential si es necesario)
RUN apt-get update && \
    apt-get install -y --no-install-recommends make build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER jovyan

COPY requirements.txt /tmp/
RUN pip install --no-cache-dir -r /tmp/requirements.txt

WORKDIR /home/jovyan
