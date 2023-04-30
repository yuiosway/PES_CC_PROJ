FROM node:16-alpine
WORKDIR /uc3
COPY ["package.json", "package-lock.json",".env", "./"]
RUN npm install
EXPOSE 5003
COPY index.js index.js
CMD [ "node","index.js" ]