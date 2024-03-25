FROM golang AS buildando

WORKDIR /app
ADD . /app
RUN go build meugo.go


FROM alpine

WORKDIR /data
COPY --from=buildando /app/meugo /data/

ENTRYPOINT ./meugo