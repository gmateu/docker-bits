#docker build -t ngnix .
#docker container run --rm --name nginx -p 80:80 -v $(pwd)/www:/usr/share/nginx/html nginx
FROM nginx:latest

WORKDIR /usr/share/nginx/html

COPY index.html index.html

