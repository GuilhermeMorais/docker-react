# Getting the image to build the node
FROM node:alpine AS build
WORKDIR /app

#Building the image.
COPY package.json .
RUN npm install

COPY . .
RUN npm run build

# Getting the image to create the live container
FROM nginx
COPY --from=build /app/build /usr/share/nginx/html

# Start command.
# for nginx you don't have a start up command.