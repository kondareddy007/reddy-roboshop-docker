FROM node:18

WORKDIR /opt/server/

EXPOSE 8080

ENV MONGO=true

COPY package.json /opt/server/

COPY server.js /opt/server/

RUN npm install

CMD ["node", "server.js"]