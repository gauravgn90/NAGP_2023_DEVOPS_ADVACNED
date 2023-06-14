FROM node:14

WORKDIR /app

COPY package*.json ./

COPY .env ./
COPY app.js ./

RUN npm install

EXPOSE 3000

CMD [ "npm", "start" ]
