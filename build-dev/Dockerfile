FROM python:3.11
LABEL maintainer 'Aluno Teste <aluno at teste.com.br>'

RUN useradd www && \
    mkdir /app && \
    mkdir /log && \
    chown www /log

USER www
VOLUME /log
WORKDIR /app
EXPOSE 8000

ENTRYPOINT ["/usr/local/bin/python"]
CMD ["run.py"]

# comando no terminal
# docker image build -t ex-build-dev .
# docker container run -it  -v $(pwd):/app -p 8010:8000 --name python-server ex-build-dev
# so acessar o browser no localhost:8010