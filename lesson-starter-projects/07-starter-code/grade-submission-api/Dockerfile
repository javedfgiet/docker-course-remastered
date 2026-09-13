## Base Image
FROM node:14

## Working Directory
WORKDIR /app

## Copy Package.json to WORK dir i.e. /app
COPY package.json .
COPY package-lock.json .

	## Instead of two line above we can copy both file as belo
	## COPY package*.josn

## Install Dependencies
RUN npm install

## Copy Source code
COPY . .

## Expose container port
EXPOSE 3000

## Commands to execute application
CMD ["node","app.js"]