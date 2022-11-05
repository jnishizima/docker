# docker

# para rodar um container, caso nao tenha ele vai baixar um container
docker container run hello-world
-----------------------------------------------------------------------------------------------------------------
# para ver qual container estao ativos
docker container ps
-----------------------------------------------------------------------------------------------------------------

# para ver qual container foram criado e comando usado
docker container ps -a
-----------------------------------------------------------------------------------------------------------------

# o 1 comando verifica a versao do bash na sua maquina local e o 2 comando verifica qual versao do bash que veio com o container
bash --version
docker container run debian bash --version
-----------------------------------------------------------------------------------------------------------------

# criando o container e acessando dentro dele para testar comando no terminal do container
docker container run -it debian bash
touch curso-docker.txt
ls curso-docker.txt
exit
# apos sair e usar o comando <run> novamente, ele acaba criando um novo container
docker container run -it debian bash
ls curso-docker.txt
ls: cannot access 'curso-docker.txt': No such file or directory
# a prova que ele criou outro container e nao esta acessando mas o mesmo
-----------------------------------------------------------------------------------------------------------------

# Containers devem ter nomes unicos, ao tentar executar novamente ele gera um erro, mostrando que ja possui esse nome de container
docker container run --name  mydeb -it debian bash
-----------------------------------------------------------------------------------------------------------------
# mostrar todos os containers indepedente do seu estado
docker container ls -a
-----------------------------------------------------------------------------------------------------------------

# para acessar um container que ja foram criado
docker container start -ai <nome>
-----------------------------------------------------------------------------------------------------------------

# mapear portas dos containers
docker container run -p 8080:80 nginx
# verificando se esta funcionando ou pelo browser acessando http://localhost:8080
curl http://localhost:8080

# mapeando diretorios para o container
docker container run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx

# mapeando diretorios para o container e rodar em background
docker container run -d --name ex-daemon-basic -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx
# para parar o container 
docker container stop ex-daemon-basic