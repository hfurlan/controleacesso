# controleacesso
Software para controle de acesso em condominios que utilizam equipamentos de biometria (virdi) ou linear.

# aprendizado
Estou utilizando este projeto para sevir de aprendizado para desenvolvimento node.js + mongoDB + openshift. A ideia é criar o ambiente de desenvolvimento local e utilizar as ferramentas do openshift para deploy (ci/cd).

1) codigo-fonte

Repositorio do GitHub (https://github.com/hfurlan/controleacesso.git). Para baixar o fonte utilizar:

git clone https://github.com/hfurlan/controleacesso.git

Repositorio publico

2) instalar o mongo-db via docker na maquina local

docker search mongo

https://www.thachmai.info/2015/04/30/running-mongodb-container/

mkdir ~/data
sudo docker run -d -p 27017:27017 -v ~/data:/data/db mongo

2.1) Popular a base com as tabelas

db.createCollection('pessoas')
db.createCollection('veiculos')
db.createCollection('eventos')

-----------------------------------
Para montar um docker com Node.js seguir o tutorial abaixo:

https://nodejs.org/en/docs/guides/nodejs-docker-webapp/

-- build
docker build -t hfurlan/controleacesso .

-- run
docker run -p 18080:8080 -d hfurlan/controleacesso
