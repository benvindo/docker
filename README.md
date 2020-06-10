***Comandos uteis Docker***

>docker run dockersamples/static-site

>docker run -d dockersamples/static-site

*Acessando o site*
>docker run -d -P dockersamples/static-site

*Nomeando um container*
>docker run -d -P --name meu-site dockersamples/static-site

>docker stop meu-site

*Definindo uma porta específica*
>docker run -d -p 12345:80 dockersamples/static-site

*Atribuindo uma variável de ambiente*
>docker run -d -P -e AUTHOR="Bruno C" dockersamples/static-site

*Parando todos os containers de uma só vez*
>docker stop $(docker ps -q)

>docker stop -t 0 $(docker ps -q)

*Rodando código em um container*
>docker run -v "C:\Users\bruno.costa\Documents\Projetos\Docker\volume-exemplo:/var/www" node

>docker run -v "C:\Users\bruno.costa\Documents\Projetos\Docker\volume-exemplo:/var/www" node npm start

>docker run -p 8080:3000 -v "C:\Users\bruno.costa\Documents\Projetos\Docker\volume-exemplo:/var/www" node npm start

>docker run -p 8080:3000 -v "C:\Users\bruno.costa\Documents\Projetos\Docker\volume-exemplo:/var/www" -w "/var/www" node npm start

>docker run -p 8080:3000 -v "$(pwd):/var/www" -w "/var/www" node npm start


*Criando a imagem*

>docker build -f Dockerfile -t bruno/node .

>docker run -d -p 8080:3000 bruno/node

*Enviar e baixar imagem docker*

>docker tag bruno/node benvindo/node

>docker push benvindo/node

>docker pull benvindo/node

*Rede própria do Docker*

>docker network create --driver bridge minha-rede

>docker run -it --name meu-container-de-ubuntu --network minha-rede ubuntu

>docker run -it --name segundo-ubuntu --network minha-rede ubuntu

>root@dee7e0da464b:/#: ping meu-container-de-ubuntu


*Pegando dados de um banco em um outro container*

>docker pull douglasq/alura-books:cap05
>docker pull mongo

>docker run -d --name meu-mongo --network minha-rede mongo

>docker run --network minha-rede -d -p 8080:3000 douglasq/alura-books:cap05

- http://localhost:8080/seed/ 
- http://localhost:8080/

*Run/Build Docker-Composer*

>docker-compose build

>docker-compose up -d

>docker-compose ps

>docker exec -it alura-books-1 ping alura-books-2

>docker exec -it alura-books-1 ping node2