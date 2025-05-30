# educaods/backend/Dockerfile
# Usar uma imagem base oficial do Python
FROM python:3.11-slim-buster 

# Definir o diretório de trabalho dentro do contêiner
WORKDIR /app # Define o diretório de trabalho padrão dentro do contêiner. Todos os comandos subsequentes serão executados a partir deste diretório.

# Copiar o arquivo requirements.txt primeiro para otimizar o cache do Docker
COPY requirements.txt . 

# Instalar as dependências Python
RUN pip install --no-cache-dir -r requirements.txt 


COPY . . 

# Expondo a porta que o Django vai usar 
EXPOSE 8000 