FROM node:16-alpine as builder
WORKDIR /app
COPY . .

RUN npm ci 
RUN npm run build
ENV NODE_ENV production
EXPOSE 3000
CMD ["npx","serve","build"]
# FROM nginx:1.21.0-alpine as production

# COPY --from=builder /app/build /usr/share/nginx/html
# COPY nginx.conf /etc/nginx/conf.d/default.conf
# EXPOSE 80
# CMD ["nginx", "-g", "daemon off;"]