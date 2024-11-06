FROM node:14 AS base
#In some languages like python we need to install some instructions on 
#the container itself regardless the environment.
#to be used for both development and production environments. So we use the base stage.

FROM node:14 AS development
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
EXPOSE 4000
CMD [ "npm", "run", "start-dev" ]

FROM node:14 AS production
WORKDIR /app
COPY package.json .
RUN npm install --only=production
COPY . .
EXPOSE 4000
CMD [ "npm", "run", "start" ]
