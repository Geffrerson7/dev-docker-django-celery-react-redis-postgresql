# Usamos la imagen oficial de Python 3.12
FROM python:3.12.8-slim

# Configuramos el directorio de trabajo
WORKDIR /app

# Instalamos dependencias del sistema operativo
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    curl && \
    rm -rf /var/lib/apt/lists/*

# Copiamos los archivos de dependencias
COPY requirements.txt /app/

# Instalamos las dependencias de Python
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Copiamos el código del proyecto
COPY . /app/

# Configuramos variables de entorno
ENV PYTHONUNBUFFERED=1

# Exponemos el puerto 8000 (el puerto por defecto de Django)
EXPOSE 8000

# Comando para ejecutar el servidor de desarrollo de Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
