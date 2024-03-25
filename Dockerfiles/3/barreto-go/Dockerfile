FROM golang AS buildando

WORKDIR /app
ADD . /app
RUN cd hello && go build meugo.go

FROM alpine

WORKDIR /data
COPY --from=buildando /app/hello/meugo /data/

ENTRYPOINT ./meugo