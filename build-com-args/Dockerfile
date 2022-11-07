FROM debian
LABEL maintainer 'Aluno <aluno at aulo.com.br>'

ARG S3_BUCKET=files
ENV S3_BUCKET=${S3_BUCKET}

# comando para executar no terminal para dar o build
# docker image build -t ex-build-arg .
# comando no container para rodar com argumentos
# docker container run ex-build-arg bash -c 'echo $S3_BUCKET'
# vai retornar: files
# agora se rodar o seguinte comando
# docker image build --build-arg S3_BUCKET=myapp -t ex-build-arg .
# docker container run ex-build-arg bash -c 'echo $S3_BUCKET'
# vai retornar: myapp