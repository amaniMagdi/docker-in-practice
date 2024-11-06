FROM node:14
WORKDIR /app
COPY package.json .
# this argument will be sent from docker-compose file
ARG NODE_ENV 
# using \ means will continue the code in the next line
RUN if ["$NODE_ENV" = "production" ];\ 
# --only=production will install only production dependencies
then npm install --only=production;\
else npm install;\
fi
COPY . .
EXPOSE 4000
CMD [ "npm", "run", "start-dev" ]
