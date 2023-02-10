# Use uma imagem base existente
FROM node:17

# Defina o diretório de trabalho
WORKDIR /app

# Copie os arquivos da sua aplicação Vue para o diretório de trabalho
COPY . /app

# Instale as dependências da aplicação
RUN npm install

# Exponha a porta 8080 para que a aplicação possa ser acessada externamente
EXPOSE 8080

# Defina o comando a ser executado quando o container for iniciado
CMD ["npm", "run", "serve"]
