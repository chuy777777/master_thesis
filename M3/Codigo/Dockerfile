# Usamos la imagen oficial de Ultralytics que ya tiene PyTorch y YOLO
FROM ultralytics/ultralytics:latest

# Creamos y nos movemos a la carpeta de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Actualizar e instalar 
RUN apt-get update && apt-get install -y --no-install-recommends \
    v4l-utils \
    fonts-dejavu-core \
    fontconfig \
    && rm -rf /var/lib/apt/lists/*

# Copiamos el archivo de requerimientos al contenedor
COPY requirements.txt .

# Si tienes librerías extra, las instalamos
RUN pip install --no-cache-dir -r requirements.txt

# Hace que el contenedor se quede durmiendo para siempre y no se apague
CMD ["tail", "-f", "/dev/null"]
