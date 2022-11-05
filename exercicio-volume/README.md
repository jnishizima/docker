# mapeando diretorios para o container
docker container run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx