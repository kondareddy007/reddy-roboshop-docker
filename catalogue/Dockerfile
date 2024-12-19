FROM node:18
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server
ENV MONGO=true
RUN chown roboshop:roboshop /opt/server
USER roboshop
COPY package.json /opt/server/
COPY server.js /opt/server/
RUN npm install
CMD ["node", "server.js"]


#docker containers can not communicate each other through they use docker default n/w.
#Roboshop project it will create own network. 
#you should not use docker default network, you should create docker own network.
#docker build -t catalogue:1 .
#docker run -d catalogue:1
#docker logs 59fd45eab65d
#docker network create roboshop
#docker network ls
#ifconfig -->you can see roboshop network with network id.
#docker network iP like modem-->172.18.0.1
#docker rm -f `docker ps -a -q`
#docker run -d --name mongodb --network=roboshop mongodb:1
#docker ps
#docker inspect <contaner id> --> mongodb ip "172.18.0.2"
#docker run -d --name catalogue --network=roboshop catalogue:1
##docker ps
##docker inspect <contaner id> --> catalogue ip "172.18.0.3"
#docker logs catalogue --> msg: mongodb connected

#docker containers can not communicate each other through they use docker default n/w.
#docker build -t mongodb:1 .
#docker run -d mongodb:1
#docker logs 59fd45eab65d
#docker inspect 59fd45eab65d
#docker network create roboshop
#docker run -d --name mongodb --network=roboshop mongodb:1
#docker run -d --name catalogue --network=roboshop catalogue:1
#docker run -d -p 80:80 --name web --network=roboshop web:1