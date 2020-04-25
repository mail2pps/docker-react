#Multi step build process


# Specify the base image
FROM node:alpine

WORKDIR /app/

#install some dependecis
COPY ./package.json ./
RUN npm install # --silent
COPY ./ ./
RUN npm run build

#Run Phase
FROM nginx
EXPOSE 80
COPY --from=0 /app/build /usr/share/nginx/html/
#CMD will automatically be executed.
