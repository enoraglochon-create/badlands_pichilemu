# Imagen base pública de Jupyter con Python
FROM jupyter/scipy-notebook:latest

USER root

# Instala dependencias del sistema necesarias para Badlands
RUN apt-get update && apt-get install -y \
    git gdal-bin libgdal-dev python3-gdal libnetcdf-dev netcdf-bin \
    && rm -rf /var/lib/apt/lists/*

# Instala Badlands desde el repositorio público de GitHub (en modo editable)
RUN pip install --no-cache-dir git+https://github.com/badlands-model/pyBadlands.git

# Instala dependencias adicionales si las necesitas (ejemplo matplotlib, rasterio, etc.)
RUN pip install --no-cache-dir \
    pandas numpy matplotlib rasterio h5py geopandas

# Copia tus notebooks y archivos al contenedor
COPY . /home/jovyan/

# Define el directorio de trabajo por defecto
WORKDIR /home/jovyan

# Establece permisos adecuados
RUN chown -R jovyan:users /home/jovyan

USER jovyan
