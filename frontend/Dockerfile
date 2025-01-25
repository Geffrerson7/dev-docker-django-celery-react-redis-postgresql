# Usamos la imagen oficial de Node 18
FROM node:22.13-alpine3.21

# Establecemos el directorio de trabajo
WORKDIR /app

# Copiamos el package.json y package-lock.json
COPY package*.json /app/

# Instalamos las dependencias
RUN npm install

# Copiamos el código fuente
COPY . /app/

# Exponemos el puerto 5173
EXPOSE 5173

# Comando para ejecutar el proyecto en modo desarrollo
CMD ["npm", "run", "dev"]