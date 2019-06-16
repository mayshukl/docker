# Base Image
FROM node:alpine

WORKDIR /usr/app

COPY ./package.json ./

#Dependencies 
RUN npm install

COPY ./ ./

EXPOSE 8081

#Default Command
CMD ["npm","start"]
