FROM nginx:lastest
LABEL maintainer 'Aluno teste <aluno at teste.com.br>'

RUN echo '<h1> Sem Conteudo </h1>' > /usr/share/nginx/html/conteudo.html
COPY *.html /usr/share/nginx/html/

# comando
# docker image build -t ex-build-copy
# docker container run -p 80:80 ex-build-copy