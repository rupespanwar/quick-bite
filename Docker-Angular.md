# Dockerfile to build angular app
```
#Build Stage
FROM node:alpine
WORKDIR /src
COPY package*.json ./
RUN npm set strict-ssl false
RUN npm config set registry http://registry.npmjs.org/
RUN npm install
COPY . .
RUN npm install -g @angular/cli@latest
RUN npm install --save-dev @angular-devkit/build-angular
# generate build
RUN ng build --output-path=/dist
RUN ls -ld  *
RUN ls -ld src/*
RUN rm -rf src/*


# stage 2
FROM nginx:alpine
WORKDIR /usr/src/app
RUN rm -rf /usr/share/nginx/html/*
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=0 /dist /usr/share/nginx/html
RUN ls -ld /usr/share/nginx/html/*
EXPOSE 4200
CMD ["nginx","-g","daemon off;"]
```


# Nginx config file, nginx.conf
```
server {
    listen  80;

    root /usr/share/nginx/html;
    index index.html;

    server_name _;

    location / {
        try_files $uri /index.html;
    }
}

```
