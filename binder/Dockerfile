FROM jupyter/base-notebook:latest
USER root

# Instalar herramientas necesarias para compilar paquetes como badlands
RUN apt-get update && \
    apt-get install -y --no-install-recommends make build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER jovyan

# Copiar requirements.txt desde binder/
COPY binder/requirements.txt /tmp/

# Instalar dependencias de Python
RUN pip install --no-cache-dir --upgrade pip setuptools wheel
RUN pip install --no-cache-dir -r /tmp/requirements.txt || true
RUN cat /root/.cache/pip/log/*.log || echo "No log files"

WORKDIR /home/jovyan
