# Etapa 1: Usar una imagen oficial de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo
WORKDIR /app

# Instalar pnpm globalmente dentro del contenedor
# Esta es la forma recomendada de usar pnpm en Docker
RUN npm install -g pnpm

# Copiar los archivos de definición de dependencias.
# pnpm usa 'pnpm-lock.yaml'. Copiarlos primero optimiza la caché de Docker.
COPY app/package.json app/pnpm-lock.yaml ./

# Instalar dependencias usando el comando de pnpm
RUN pnpm install

# Copiar el resto del código de la aplicación
COPY app/. .

# Exponer el puerto de Next.js
EXPOSE 3000

# Comando para iniciar el servidor de desarrollo con pnpm
CMD ["pnpm", "dev"]