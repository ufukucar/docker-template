FROM node:alpine

WORKDIR /var/www/public

COPY package*.json ./

RUN npm install --silent

# copy all files
COPY . .

EXPOSE 5173

CMD ["npm", "run", "dev"]

