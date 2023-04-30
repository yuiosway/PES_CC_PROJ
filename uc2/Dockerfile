FROM node:16-alpine
WORKDIR /uc2
COPY ["package.json", "package-lock.json",".env", "./"]
RUN npm install
EXPOSE 5002
COPY index.js index.js
CMD [ "node","index.js" ]