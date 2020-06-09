***Comandos uteis Docker***

docker run dockersamples/static-site

docker run -d dockersamples/static-site

>Acessando o site
docker run -d -P dockersamples/static-site

>Nomeando um container
docker run -d -P --name meu-site dockersamples/static-site

docker stop meu-site

>Definindo uma porta específica
docker run -d -p 12345:80 dockersamples/static-site

>Atribuindo uma variável de ambiente
docker run -d -P -e AUTHOR="Bruno C" dockersamples/static-site

>Parando todos os containers de uma só vez
docker stop $(docker ps -q)

docker stop -t 0 $(docker ps -q)

>Rodando código em um container

docker run -v "C:\Users\bruno.costa\Desktop\volume-exemplo:/var/www" node

docker run -v "C:\Users\Alura\bruno.costa\volume-exemplo:/var/www" node npm start

docker run -p 8080:3000 -v "C:\Users\bruno.costa\Desktop\volume-exemplo:/var/www" node npm start

docker run -p 8080:3000 -v "C:\Users\Alura\bruno.costa\volume-exemplo:/var/www" -w "/var/www" node npm start

docker run -p 8080:3000 -v "$(pwd):/var/www" -w "/var/www" node npm start