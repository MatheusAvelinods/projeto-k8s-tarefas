# imagem leve do Node
FROM node:18-alpine

# Define o diretório de trabalho dentro do container
WORKDIR /app

# Copia os arquivos de dependências primeiro (para aproveitar o cache)
COPY package*.json ./

# Instala as dependências
RUN npm install

# Copia o restante do código do projeto
COPY . .

# Expõe a porta que o servidor
EXPOSE 3003

# Comando para iniciar a aplicação
CMD ["node", "main.js"]