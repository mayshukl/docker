# Specify base Image
FROM node:alpine

WORKDIR /usr/app
# Install Dependencies
COPY ./package.json ./

RUN npm install

COPY ./ ./

EXPOSE 8080

# Default Command
CMD ["npm","start"]