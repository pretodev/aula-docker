# Use a imagem base do Node.js
FROM node:18

# Defina o diretório de trabalho no contêiner
WORKDIR /usr/src/app

# Copie o package.json e package-lock.json para o diretório de trabalho
COPY package*.json ./

# Instale as dependências do projeto
RUN npm install

# Copie o restante dos arquivos da aplicação
COPY . .

# Exponha a porta em que a aplicação vai rodar
EXPOSE 3000

# Comando para rodar a aplicação
CMD ["node", "src/index.js"]
