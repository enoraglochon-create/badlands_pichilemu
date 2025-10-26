# Imagen base oficial de Jupyter con Python
FROM jupyter/base-notebook:latest

# Cambiar a usuario root para instalar paquetes del sistema si es necesario
USER root

# (Opcional) Instalar paquetes del sistema si los necesitas
# RUN apt-get update && apt-get install -y <paquetes>

# Volver al usuario jovyan (recomendado por Binder)
USER jovyan

# Copiar el archivo de requerimientos
COPY binder/requirements.txt /tmp/

# Instalar dependencias de Python
RUN pip install --no-cache-dir -r /tmp/requirements.txt

# Establecer el directorio de trabajo
WORKDIR /home/jovyan
