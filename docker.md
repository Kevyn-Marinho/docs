# DOCKER

### Exemplo 

```
FROM node:14
WORKDIR /app
COPY . .
RUN npm install 
ENTRYPOINT npm start
```
* FROM - referente a imagem base que vai ser executada, no caso, node versão 14 
* WORKDIR  - referente ao diretório do contexto onde os comandos vão ser executados, assim, não necessita de se escrever o nome do diretório sempre 
* COPY - faz a cópia de arquivos para uma pasta do container, o primeiro '.' refere-se a pasta atual e o segundo ao workdir definido anteriormente 
* RUN - executa um comando durante a criação do container, como no caso era uma aplicação node, foir realizado o npm install 
* ENTYPOINT - refere-se ao comando que vai ser executado assim que o container iniciar, como no caso era uma aplicação node, npm start para subir a aplicação


Após a criação do arquivo é necessário criar a imagem, para isso, executar o comando 
```
docker build -t kevynmarnho/appnode:1.0 .
```

* docker build - é o comando responsável pela criação de imagens docker 
* -t - parametro para nomear a imagem, no caso kevynmarinho/appnode 
* :1.0 - versão da imagem 
* . - caminho do dockerfile a ser executado 

Após a criação da imagem, para o serviço estar disponível é necessário rodar a imagem, para isso, executar o comando
```
docker run -d -p 8080:3000 kevynmarinho/appnode:1.0
```

* docker run - comando responsável por executar o container 
* -d - desvincula o terminal que você está usando, do terminal do container
* -p - associa uma porta local a uma porta do container
* 8000:3000 - portas a serem associadas, na esquerda a porta local, na direita a porta do container 
 

### Evoluindo o dockerfile 

```
FROM node:14
ARG PORT_BUILD=6000
EXPOSE $PORT_BUILD
ENV PORT=$PORT_BUILD
WORKDIR /app
COPY . .
RUN npm install 
ENTRYPOINT npm start
```

* ARG - Refere-se a variáveis que serão utilizadas em tempo de build do container
* PORT_BUILD=6000 - Refere-se a uma variável de tempo de build que pode ser usada dentro do próprio dockerfile chamada 'PORT_BUILD' com o valor '6000'
* EXPOSE $PORT_BUILD - Refere-se a porta que o container vai export para o sistema local, com o valor da variável $PORT_BUILD
* ENV PORT=$PORT_BUILD - Refere-se as variáveis de ambiente que podem ser acessadas pela aplicação, no caso, por ser node, através do comando 'proccess.env ' 


