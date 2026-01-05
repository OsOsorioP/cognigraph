# Usar la imagen oficial de Python que ya descargamos manualmente
FROM python:3.11-slim

# Establecer el directorio de trabajo
WORKDIR /app

# Instalar poetry (una mejor práctica para gestionar dependencias en Python)
RUN pip install poetry

# Copiar solo los archivos de dependencias para aprovechar el cacheo
COPY pyproject.toml poetry.lock* ./

# Instalar las dependencias del proyecto sin instalar las de desarrollo
RUN poetry install --no-root 

# Copiar el resto del código de la aplicación
# El punto de entrada será /app/app
COPY ./app /app/app

# [Opcional pero recomendado] Añadir un script de inicio para esperar a la BD
# Por ahora, lo omitimos para mantenerlo simple.