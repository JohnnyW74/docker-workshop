FROM golang:alpine
WORKDIR /app
COPY ./hello.go /app
RUN go build -o goapp
ENTRYPOINT ["/app/goapp"]
