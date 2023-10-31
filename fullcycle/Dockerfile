FROM golang:alpine AS builder

WORKDIR /app

COPY ./main.go /app

RUN go mod init app

RUN go get -d -v

RUN go build -o ./desafiogo

FROM scratch

COPY --from=builder /app /app

CMD [ "/app/desafiogo" ]