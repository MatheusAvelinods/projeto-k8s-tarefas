# --- Estágio 1: Build (Construção) ---
FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
# Gera a pasta 'dist' ou 'build' com os arquivos estáticos
RUN npm run build

# --- Estágio 2: Produção (Servidor Nginx) ---
FROM nginx:alpine

# Copia os arquivos gerados no estágio anterior para a pasta do Nginx
COPY --from=build /app/build /usr/share/nginx/html

# Expõe a porta 80 (padrão web)
EXPOSE 80

# Inicia o Nginx
CMD ["nginx", "-g", "daemon off;"]