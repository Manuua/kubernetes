# base da imagem Docker a ser utilizada
FROM python:3.9-alpine

# adicionar a camada que será o diretório padrão a ser utilizado
WORKDIR /pod

# copiar os arquivos da pasta src (source) para diretório padrão do container
COPY ./app /pod/app

# copiar o arquivo de instalação dos requisitos do ambiente
COPY requirements.txt /pod

# rodar um comando para instalar os pacotes necessários 
RUN pip install -r requirements.txt

# comando a ser rodado dentro do container para rodar o servidor da api
ENTRYPOINT ["uvicorn", "app.main:app","--workers","1","--host", "0.0.0.0", "--port", "8000"]